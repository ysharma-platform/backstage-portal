# Backstage Portal

A production-grade [Backstage](https://backstage.io) developer portal, built end-to-end via **Spec-Driven Development** using [GitHub SpecKit](https://github.com/github/spec-kit), deployed locally to a real multi-node `kind` Kubernetes cluster, designed to migrate cleanly to Amazon EKS.

## Local development

```sh
yarn install
yarn start
```

This runs the frontend (`packages/app`) on `http://localhost:3000` and the backend (`packages/backend`) on `http://localhost:7007` concurrently.

## How this project is organized

- **Arc** — a theme of work (Foundations, GitOps, Observability, Auth, ...), tracked as a [Milestone](../../milestones)
- **Chapter** — one SpecKit feature (`specs/NNN-name/`), scoped to a single small, independently reviewable PR
- Every cross-cutting or hard-to-reverse decision is recorded as an ADR under `docs/adr/`
- Progress is tracked on the [Backstage Portal Roadmap project board](https://github.com/orgs/ysharma-platform/projects/1)

## Non-negotiables

- **Security by design** — every feature guards against classic and AI-specific attack vectors (untrusted catalog/TechDocs/template content is always treated as data, never instructions); dependency, image, secret, and SAST scanning gate every merge.
- **Full test pyramid** — unit, integration, contract, and e2e tests, scoped to what's meaningful per chapter, with enforced coverage thresholds.
- **Infrastructure as typed code** — all Kubernetes resources are authored as [CDK8s](https://cdk8s.io) TypeScript, never hand-written YAML.
- **Local mirrors production** — multi-node cluster, real resource sizing, TLS, GitOps-driven deploys, a full observability stack. No "works on my kind cluster" shortcuts.

## Status

🚧 Just getting started — see the [Project board](https://github.com/orgs/ysharma-platform/projects/1) for current progress.

## License

[MIT](LICENSE)
