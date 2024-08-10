# OpenTelemetry Collector and Prometheus Setup

This repository contains a Docker Compose setup for running the OpenTelemetry Collector and Prometheus. The OpenTelemetry Collector is configured to receive metrics and expose them for Prometheus to scrape.

## Prerequisites

- Docker
- Docker Compose
- `mkdir metrics_output`
- `chmod 777 metrics_output`

## Running service

- `docker-compose up -d`
- Post a metric to the otel collector
  ```commandline
    curl -X POST http://localhost:4318/v1/metrics \
  -H "Content-Type: application/json" \
  -d '{"resourceMetrics":[{"scopeMetrics":[{"metrics":[{"name":"isengard-metric","gauge":{"dataPoints":[{"asInt":"34"}]}}]}]}]}'
    ```


Verify the services
- http://localhost:9090/graph


