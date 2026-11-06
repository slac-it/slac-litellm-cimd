# LiteLLM MCP Gateway OAuth Client Metadata

This repository contains OAuth client metadata documents for the SLAC LiteLLM
MCP Gateway. The production and development documents are kept separate so
each environment can use its own callback URL.

| File | Environment | Redirect URI |
| --- | --- | --- |
| [`ai-api.json`](ai-api.json) | Production | `https://ai-api.slac.stanford.edu/callback` |
| [`ai-api-dev.json`](ai-api-dev.json) | Development | `https://ai-api-dev.slac.stanford.edu/callback` |

Both documents identify the client as **LiteLLM MCP Gateway** and specify the
authorization-code and refresh-token grant types, the authorization-code
response type, and `none` for token endpoint authentication.

## Maintenance

When updating a document, keep its `client_id` URL and registered redirect URI
aligned with the intended environment. The redirect URI must exactly match the
callback configured for that environment. Keep the production and development
settings in their respective files.

Pushes to `main` automatically deploy the static content to GitHub Pages.
GitHub Actions are pinned to full commit SHAs to satisfy the repository's action
policy. Dependabot checks daily for action updates and opens pull requests;
merge those updates to keep the pins current.
