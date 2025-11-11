# shiny-gateway

new gateway

## Overview

This MCP Gateway configuration includes **1** MCP server with **0** total tools, **0** of which are exposed.

### MCP Servers

- **com.stripe/mcp** (com.stripe/mcp)

## Configuration Files

- `sources.yaml`: MCP server bindings and connection details
- `gateway.yaml`: Gateway configuration with exposure rules
- `resolved/catalog.json`: Resolved catalog with exposed tools only

## Deployment

### Docker Compose

```bash
docker-compose up -d
```

The gateway will be available at `http://localhost:8080`.

### Kubernetes

Apply the CRD manifests:

```bash
kubectl apply -f mcp-sources.yaml
kubectl apply -f gateway-config.yaml
```

## Security Notes

- All secrets use `vault://` or `env://` URIs (no plaintext secrets)
- Default exposure policy is deny-all; only explicitly allowed tools are exposed
- Review exposure rules in `gateway.yaml` before deployment

## Generated

Generated on 2025-11-11T16:33:48.131Z
