# Wallabag Helm Chart

This Helm chart deploys Wallabag v2.5.2, a self-hosted read-it-later application, on Kubernetes using SQLite as the database backend.

## Description

Wallabag is a self-hosted application that allows you to save web pages for later reading. This Helm chart provides a simple way to deploy Wallabag on Kubernetes with persistent storage using hostPath for SQLite database storage.

## Prerequisites

- Kubernetes 1.16+
- Helm 3.0+
- PV provisioner support in the underlying infrastructure

## Installing the Chart

To install the chart:

```bash
helm install wallabag .
```

## Configuration

The following table lists the configurable parameters of the Wallabag chart. Modify the `values.yaml` file to customize the installation.

| Parameter | Description | Default |
|-----------|-------------|---------|
| `image.repository` | Wallabag image repository | `wallabag/wallabag` |
| `image.tag` | Wallabag image tag | `2.5.2` |
| `persistence.enabled` | Enable persistence for SQLite database | `true` |
| `persistence.hostPath` | Host path for SQLite database storage | `/path/to/data` |

## Persistence

This chart uses a hostPath PersistentVolume for storing the SQLite database. Make sure the specified host path exists and has the correct permissions.

## Accessing Wallabag

Once deployed, Wallabag will be available at the configured ingress host or service endpoint. The default login credentials are:

- Username: `wallabag`
- Password: `wallabag`

Please change these credentials after the first login.

## License

This Helm chart is open-source and available under the MIT license.
