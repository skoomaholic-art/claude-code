# Claude Code through OpenRouter

This repository is an upstream-style Claude Code fork. Do not patch Claude Code's internal transport just to add OpenRouter. Configure the supported Anthropic-compatible endpoint at runtime instead.

## Shell configuration

Keep the real key outside Git:

```bash
export OPENROUTER_API_KEY="<your-new-openrouter-key>"
export ANTHROPIC_BASE_URL="https://openrouter.ai/api"
export ANTHROPIC_AUTH_TOKEN="$OPENROUTER_API_KEY"
export ANTHROPIC_API_KEY=""
```

Then start Claude Code normally:

```bash
claude
```

Do not commit these values to this repository. In particular, a normal project `.env` file is not the right place to configure the native Claude Code process; use the shell/session environment or your managed runtime settings.

OpenRouter model selection can be configured separately when needed. Keep model identifiers in non-secret configuration and keep `OPENROUTER_API_KEY` only in the environment/secret store.
