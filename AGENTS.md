# Shopify app development

This app is scaffolded from a Shopify app template. See the README for framework-specific details.

Use the [Shopify AI Toolkit](https://shopify.dev/docs/apps/build/ai-toolkit) for all Shopify API and platform work. If missing, install it in the agent host per that page (or `npx skills add Shopify/shopify-ai-toolkit --list` for skill-compatible hosts) — do not add tooling to this repo.

## Field registry architecture (frozen)

This decision applies to all future work in this repository. Preserve the field registry's three-file structure. Do not add, remove, split, merge, or rename registry files, or introduce a parallel registry, unless the project owner explicitly revises this decision.

Use the canonical registry definitions across filtering, editing, imports, exports, and spreadsheet operations. Make shared field definition changes in the registry and have each consumer reuse those definitions directly or through a derived catalog or adapter. Do not maintain independent copies in individual features.

The backend is the authoritative enforcement point for operational feature availability and authorization. Check both on the server before accepting or executing an operation. Registry metadata and frontend controls may describe or display capabilities, but they do not grant access or replace backend checks.
