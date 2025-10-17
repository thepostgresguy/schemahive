# SchemaHive

SchemaHive is a comprehensive data schema management platform that helps teams track, validate, and evolve their data contracts across diverse data sources.

## Project Structure

```
schemahive/
	apps/
		api/                  # REST/GraphQL service for metadata dictionary, drift events, policies
		ui/                   # Web UI for dictionary, lineage, drift review, approvals
		workers/              # Schedulers, pollers, stream processors, notification executors
	packages/
		core/                 # Domain models, JSONSchemas, storage and indexing, versioning
		ai-engine/            # Drift detection, mapping, LLM orchestration, embeddings, prompts
		connectors/           # Source adapters: db/warehouse/lake/stream/catalogs
		rules/                # Normalization, contracts, synonyms, deprecations, policies
		sdk-js/               # JS/TS client SDK for UI and Node integrations
		sdk-py/               # Python SDK/CLI for data teams and pipelines
		cli/                  # schemahive CLI: init, run, diff, approve, export
	data/
		samples/              # Example schemas, drift cases, fixtures
		migrations/           # DB migrations and baseline metadata snapshots
	infra/
		docker/               # Images, compose for local dev
		k8s/                  # Deployment manifests, Helm charts
		OpenTofu/            # Cloud infra as code
	configs/
		dev/                  # Local overrides
		prod/                 # Production defaults and secrets templates
	docs/                   # Architecture, API, connector guides, runbooks
	scripts/                # Dev and release helpers
	tests/
		e2e/                  # Cross-service scenarios
		api/                  # Service tests
		ui/                   # Frontend tests
		connectors/           # Adapter conformance tests
	.github/
		workflows/            # CI/CD pipelines, codeowners, issue templates
	LICENSE
	README.md
	CONTRIBUTING.md
```

## Folder structure (create locally)

The layout above matches a recommended repository layout. To create the full folder tree locally from the repository root, run the following command on macOS/Linux (zsh/bash):

```bash
# Create the full folder tree used in this README
mkdir -p \
	apps/api \
	apps/ui \
	apps/workers \
	packages/core \
	packages/ai-engine \
	packages/connectors \
	packages/rules \
	packages/sdk-js \
	packages/sdk-py \
	packages/cli \
	data/samples \
	data/migrations \
	infra/docker \
	infra/k8s \
	infra/terraform \
	configs/dev \
	configs/prod \
	docs \
	scripts \
	tests/e2e \
	tests/api \
	tests/ui \
	tests/connectors \
	.github/workflows
```

Tip: For Windows, use PowerShell's New-Item -ItemType Directory or WSL.

## Quick Start

```bash
# Install dependencies
npm install

# Start development environment
docker-compose up

# Run tests
npm test

# Use CLI
schemahive init     # Initialize new project
schemahive diff     # Check for schema changes
schemahive approve  # Approve schema changes
schemahive export   # Export schemas
```

## Documentation

- [Architecture Overview](docs/architecture.md)
- [API Reference](docs/api.md)
- [Connector Guide](docs/connectors.md)
- [CLI Reference](docs/cli.md)
- [Contributing](CONTRIBUTING.md)

## License

See [LICENSE](LICENSE) file for details.