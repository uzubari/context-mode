# Uninstall Context Mode From Codex CLI

For a Codex CLI install, remove context-mode from Codex configuration, hooks, routing instructions, and npm.

## 1. Remove the MCP server

Edit `~/.codex/config.toml` and delete this block:

```toml
[mcp_servers.context-mode]
command = "context-mode"
```

## 2. Remove Codex hooks

Edit `~/.codex/hooks.json` and remove hook entries whose command starts with:

```json
"context-mode hook codex ..."
```

If `~/.codex/hooks.json` only exists for context-mode, you can remove the whole file. If it contains other hooks, remove only the context-mode entries.

## 3. Remove routing instructions

If you copied the Codex routing instructions, remove the context-mode section from either:

```bash
~/.codex/AGENTS.md
./AGENTS.md
```

Only delete the whole file if it contains no other instructions you want to keep.

## 4. Uninstall the npm package

```bash
npm uninstall -g context-mode
```

## Optional: remove saved Codex context-mode data

```bash
rm -rf ~/.codex/context-mode
```

Restart Codex CLI after uninstalling.
