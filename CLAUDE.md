# Claude Code Configuration — RuFlo V3

## Who I Am

Thomas. Thinker, aspirational optimist, founder. New to software development
but AI-native — I rely on Claude to code. My job is vision, direction, and
decision-making. Your job is execution.

## My Projects

### Neurovanta (Parent Company)
Not yet live. Building toward launch.

**Seed** — three interconnected branches sharing infrastructure:
- **Cognition** — proprietary cognitive training games + rebranded BrainHQ
- **Purpose** — helps users find direction; generates custom challenges that
  progress them through a purposeful life trajectory
- **Clarity** — reflection tool that feeds into Purpose; both share one AI
  with different lenses

**Overture** — webapp that funnels groups toward convoy/group travel.
  Users join a game, answer questions, and oAI (Overture AI) outputs a full
  group itinerary + assigns roles. Monetisation: funnel to rental companies.
  Overture funds the broader portfolio.

**Status**: Neither live. Both need to be built.

## Communication Style

- Concise. No filler. Direct.
- Flag assumptions before acting on them
- End every task with a structured summary: what was done, what's next,
  any blockers
- Ask one clarifying question if the brief is ambiguous — don't guess
- When I'm vague, tell me. Don't paper over it.

## Rules for All Agents

- Do what has been asked; nothing more, nothing less
- NEVER create files unless absolutely necessary
- ALWAYS prefer editing an existing file to creating a new one
- NEVER proactively create documentation or README files unless requested
- NEVER save working files to the root folder
- NEVER commit secrets, credentials, or .env files
- ALWAYS read a file before editing it
- ALWAYS run tests after making code changes
- ALWAYS verify build succeeds before committing
- Never continuously check status after spawning a swarm — wait for results

## File Organisation

- `/src` — source code
- `/tests` — test files
- `/docs` — documentation and markdown
- `/config` — configuration files
- `/scripts` — utility scripts
- `/examples` — example code

## Project Architecture

- Domain-Driven Design with bounded contexts
- Files under 500 lines
- Typed interfaces for all public APIs
- TDD London School (mock-first) for new code
- Event sourcing for state changes
- Input validation at all system boundaries

### Swarm Config

- **Topology**: hierarchical-mesh
- **Max Agents**: 8
- **Memory**: hybrid
- **HNSW**: Enabled
- **Neural**: Enabled

## Build & Test
```bash
npm run build
npm test
npm run lint
```

## Security

- NEVER hardcode API keys or credentials
- NEVER commit .env files
- Always validate user input at system boundaries
- Always sanitize file paths

## Concurrency Rules

- All related operations run concurrently in ONE message
- Batch ALL todos in ONE TodoWrite call
- Spawn ALL agents in ONE message via Task tool
- Batch ALL file reads/writes in ONE message

## Swarm Execution

- CLI tools handle coordination: swarm init, memory, hooks, routing
- Claude Code Task tool handles ALL execution: agents, file ops, code, git
- NEVER use CLI tools as a substitute for Task tool agents
- After spawning agents, STOP — do not add more tool calls or check status
- When results arrive, review ALL before proceeding
```bash
npx ruflo@latest swarm init --topology hierarchical --max-agents 8 --strategy specialized
```

### 3-Tier Model Routing

| Tier | Handler | Use Cases |
|------|---------|-----------|
| 1 | Agent Booster (WASM) | Simple transforms — skip LLM |
| 2 | Haiku | Simple tasks, low complexity |
| 3 | Sonnet/Opus | Complex reasoning, architecture, security |

## Available Agent Types

### Core
`coder`, `reviewer`, `tester`, `planner`, `researcher`

### Specialised
`security-architect`, `memory-specialist`, `performance-engineer`

### Swarm Coordination
`hierarchical-coordinator`, `mesh-coordinator`

### SPARC
`sparc-coord`, `sparc-coder`, `specification`, `architecture`

## Memory Commands
```bash
npx ruflo@latest memory store --key "key" --value "value" --namespace patterns
npx ruflo@latest memory search --query "your query"
npx ruflo@latest memory list --namespace patterns --limit 10
npx ruflo@latest memory retrieve --key "key" --namespace patterns
```

## My Stack

- **Editor**: VS Code + Claude Code
- **Notes**: Obsidian (Secondbrain vault), Notion
- **Calendar**: Google Calendar
- **Machine**: MacBook
- **Version control**: GitHub (twbolus)
- **AI**: Claude (Anthropic) — primary interface for all build work

## Daily Start
```bash
cd ~/Desktop/Software\ Development/mainframe
npx ruflo@latest daemon start
```