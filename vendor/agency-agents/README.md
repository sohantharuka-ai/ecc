# Agency Agents (vendored)

This folder holds an unmodified copy of the agent personas from
[msitarzewski/agency-agents](https://github.com/msitarzewski/agency-agents),
licensed under MIT (see `LICENSE` in this folder).

- Upstream commit: `b859c51`
- Contents: 283 agent `.md` files grouped by division, plus 16 `strategy/`
  playbook, runbook and coordination docs.

These files are third-party content. They are kept separate from ECC's curated
`agents/` and `skills/`. They are not listed in the install manifests and are
not shipped with the ECC plugin.

## Install into Claude Code

Each file is a Claude Code subagent (Markdown with `name` and `description`
frontmatter). Copy a division, or all of them, into your agents directory:

```bash
# One division
cp vendor/agency-agents/engineering/*.md ~/.claude/agents/

# Every division (skips the strategy/ docs, which are not agents)
find vendor/agency-agents -name '*.md' -not -path '*/strategy/*' \
  -not -name README.md -exec cp {} ~/.claude/agents/ \;
```

Check for name clashes with agents you already have before copying.

## Update

Re-copy the division folders from a fresh clone of the upstream repository and
update the commit hash above.
