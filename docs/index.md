# Python Flask Demo Application

A simple Flask web application that provides REST API endpoints with system information.

## Overview

This application exposes three main endpoints that return JSON responses with timestamp, hostname, and deployment information.

## API Endpoints

### `/api/v1/details`
Returns application details with current time and hostname.

### `/api/v1/info`
Returns application information with current time and hostname.

### `/api/v1/healthz`
Health check endpoint that returns application status.

## Configuration

- **Port**: 5050
- **Host**: 0.0.0.0 (all interfaces)

## Docker

Build and run with Docker:
```bash
docker build -t python-app .
docker run -p 5050:5050 python-app
```

## Kubernetes Deployment

Deploy to `pythondemo` namespace:
```bash
kubectl apply -f k8s/
```

Test with port-forward:
```bash
kubectl port-forward -n pythondemo service/python-app-service 8080:80
curl http://localhost:8080/api/v1/healthz
```

## Dependencies

- Flask 3.0.3
- Python 3.10