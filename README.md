# Kubernetes Stateless Web App

This repository contains Kubernetes manifests for a simple stateless web app (Nginx or Node.js).

## Components
- **Deployment**: 3 replicas of Nginx (or Node.js) with environment variables from a ConfigMap
- **ConfigMap**: Defines `APP_ENV=prod`
- **Service**: ClusterIP exposing port 80
- **HPA**: Scales pods between 3 and 10 based on CPU utilization > 70%

## Prerequisites
- Kubernetes cluster (minikube, kind, or cloud provider)
- `kubectl` configured
- Metrics Server installed (for HPA)

## Deploy

```bash
kubectl apply -f configmap.yaml
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl apply -f hpa.yaml
