# VPS Agent Stack — Setup Checklist

## Infrastructure
- [x] OS hardening: SSH key-only, UFW default-deny, fail2ban, unattended-upgrades
- [x] Swap 2GB, chmod 600, swappiness=10
- [x] Node.js v20, npm, Git, tmux
- [x] Claude Code CLI
- [x] Docker Engine + Docker Compose
- [x] tony added to docker group

## Services
- [x] Qdrant (vector DB) — Docker, healthy
- [x] Redis — Docker, healthy

## Secrets
- [x] Doppler project: `tony_claude`
- [x] Gmail OAuth credentials (CLIENT_ID, CLIENT_SECRET, REFRESH_TOKEN)
- [x] GitHub token (TONY_GIT)
- [ ] Google Calendar credentials
- [ ] Telegram session

## Integrations (Step 6)
- [x] Gmail API — tested, working
- [ ] Gmail MCP server wired to Claude
- [ ] GitHub MCP server wired to Claude
- [ ] Google Calendar API + MCP

## Telegram
- [ ] Dedicated phone number
- [ ] Telethon one-time auth → session saved to ~/secrets-staging/
- [ ] MTProto listener running in tmux
- [ ] Webhook verified + forwarding to agent

## Agent Stack
- [ ] Orchestrator agent
- [ ] Code maker / bug fixer / tester agents
- [ ] Redis file locking between agents
- [ ] Qdrant collections: agent_memories, codebase, bug_fixes, feature_requests

## Automation
- [ ] Cron: nightly feature-request → dedup → implement → test → commit
- [ ] Telegram notifications on failures
