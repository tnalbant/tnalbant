### Hi, I'm Turgay (timtim)

I build macOS and iOS apps, and I send small, tested fixes to other people's open source.

Currently: **[Trailwarden](https://github.com/tnalbant/trailwarden)** — a local audit trail for coding
agents on macOS. Claude Code, Codex, Gemini CLI, opencode, Cursor, Copilot and Hermes already log what
they do on your Mac. Trailwarden reads those logs, flags the moment an agent runs something you would
have stopped, shows which agent touched which file, and turns a month of agent work into one page you
can read or hand on, redacted.

<img src="https://raw.githubusercontent.com/tnalbant/trailwarden/main/docs/screenshots/timeline-light.png" width="860" alt="Trailwarden — timeline, filters and inspector">

Local-first on purpose: no account, no server, no telemetry. The only two network reads are the update
check and the price list — both of a public file, both on your click.

- Swift / SwiftUI app, a CLI, and an MCP server other agents can query
- 27 risk rules — `rm -rf`, `curl … | sh`, keychain reads, `DROP TABLE`, and more
- Apache-2.0 · macOS 14+ · ![release](https://img.shields.io/github/v/release/tnalbant/trailwarden?style=flat-square)

```bash
brew tap tnalbant/trailwarden
brew install --cask trailwarden     # menu bar app
brew install trailwarden-cli        # CLI + MCP server
```

### In other people's projects

The same thread runs through my pull requests: security, guardrails, and refusing input that does not
parse instead of accepting it quietly. Each one reproduced before it was touched.

| Pull request | What it fixes |
|---|---|
| [oxynote#434](https://github.com/oxynote/oxynote/pull/434) | a data source URL that does not parse is rejected instead of silently accepted |
| [Ai-edit-studio#159](https://github.com/laaielichter/Ai-edit-studio/pull/159) | WebVTT caption files are read correctly on import |
| [openuni#141](https://github.com/saajann/openuni/pull/141) | inverted `from`/`to` ranges are rejected on the calendar endpoint |

[All merged pull requests](https://github.com/pulls?q=is%3Apr+author%3Atnalbant+is%3Amerged) · ![merged PRs](https://img.shields.io/github/issues-search?query=is%3Apr%20author%3Atnalbant%20is%3Amerged&label=merged%20pull%20requests&style=flat-square)

### How I work

- Reproduce first, then fix. I would rather write the test that shows the bug than argue about the fix.
- Every change ships with a test that fails without it.
- Small diffs and clear messages; no unrelated cleanup.
- Read the repository's own process before writing code.
