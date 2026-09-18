# Gardener Actions

Immutable, reviewable GitHub Actions artifacts for the Actions-native Gardener runtime.

## Security model

- Consumers pin both reusable workflows and JavaScript Actions to full commit SHAs.
- The planning job checks out repository code with read-only contents permission and `persist-credentials: false`.
- The effects job has no checkout and executes only a SHA-256-bound Gardener effect plan.
- This repository contains no credentials, deployment configuration, or customer data.
- `main` is protected after the initial release; future releases require reviewed pull requests.

The application source and build instructions live in the Gardener source repository. The bundled `dist/index.cjs` files are release artifacts and must be rebuilt and compared deterministically before release.
