# bot-prompt

A system prompt that turns AI coding agents from human-like coworkers into CLI-style tools. No praise, no apologies, no "Happy to help." Just status lines, diagnostics, and diffs.

Example:

```text
User: fix the failing tests. make no mistakes.

Agent:
status: done
changed:
  - src/parser.ts: handled empty input before tokenization
checks:
  - npm test: pass
```

[AGENTS.md](./AGENTS.md)

Blog post: https://walterra.dev/blog/2026-06-25-youre-right-to-push-back

## Installation

Copy the prompt to the persistent instructions file your agent reads.

### Pi Coding Agent

```bash
mkdir -p ~/.pi/agent
curl -fsSL https://raw.githubusercontent.com/walterra/bot-prompt/main/AGENTS.md \
  -o ~/.pi/agent/AGENTS.md
```

### Claude Code

Claude Code uses `CLAUDE.md` for user-level instructions.

```bash
mkdir -p ~/.claude
curl -fsSL https://raw.githubusercontent.com/walterra/bot-prompt/main/AGENTS.md \
  -o ~/.claude/CLAUDE.md
```

### Codex CLI

Codex uses `AGENTS.md` in `~/.codex` for global instructions.

```bash
mkdir -p ~/.codex
curl -fsSL https://raw.githubusercontent.com/walterra/bot-prompt/main/AGENTS.md \
  -o ~/.codex/AGENTS.md
```

### Cursor CLI / Cursor Agent

Cursor supports `AGENTS.md` in a project root and subdirectories. For a project-local install:

```bash
curl -fsSL https://raw.githubusercontent.com/walterra/bot-prompt/main/AGENTS.md \
  -o AGENTS.md
```

For global Cursor preferences, use **Customize → Rules** in Cursor and paste the contents of [`AGENTS.md`](./AGENTS.md). Cursor docs describe User Rules as global preferences applied across projects.
