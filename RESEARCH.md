# Personal website research

Date: 2026-10-04

Recommendation: build a small "proof of work" site: a one-page profile, four deep case studies, and a live "ask about my work" agent with public evals. For the boilerplate, start from `magicuidesign/portfolio` and use `santifer/cv-santiago` as the reference for the chat part.

## What the research says matters in 2026

- **Depth over count:** three to five well-documented projects beat many shallow demos, and one project with evals, deployment and monitoring beats several generic ones.
- **Evals are the rare skill:** in one survey about 89% of agent teams had observability but only 52% had real evals.
- **Production judgment:** hiring managers screen for people who talk about cost, failures and bad model output, not about prompting.
- **Writing:** five or more posts on specific failure modes you debugged count for more than "what is RAG" articles.
- **Agent-readable sites:** `llms.txt`, JSON-LD and an AI-crawler-friendly `robots.txt` are now standard, and portfolios with a grounded chat that answers as you are a visible trend.

## What the repos actually show

Positioning: a full-stack product engineer who ships LLM features and runs agent-driven development, not an ML engineer. The site should say that.

| Case study | Why it is strong |
|---|---|
| **Next1 360** (next1.football) | Tool-calling agent with iteration and tool budgets, admission guard before paid calls, safety layers with a red-team test corpus, cost accounting, a model-eval harness, 22 ADRs. This is the flagship. |
| **MCP servers for business data** (omnifitlab, academy CMS, omnibodypay) | Scoped read/authoring/publish tools, OAuth for claude.ai and ChatGPT connectors, data-exclusion tests, admin-issued keys. |
| **Renderia** | Multi-provider vision with structured output, image generation with reference conditioning, a mock provider for tests. It is the most visual demo. |
| **Agent development pipeline** (Sandcastle loops, skills, hooks, sub-agents across about 7 repos, plus the Fourth team workflow) | Shows how agents run against GitHub issues with a reviewer agent and guard scripts. |

Supporting pieces:

- The payment and entitlement engine (academy CMS, 1,128 commits since 2022).
- The Expo apps with in-app purchases.
- Fourth: about 88% of 2,067 commits on a micro-frontend rebuild.
- Thalassa: hotel price finder with scraping, weather scoring and email alerts.
- Claude Library: a Claude Code reference site in English and Bulgarian.

Gaps: no RAG, embeddings or vector search in any repo, and the evals are scenario-based rather than a benchmark suite. The site's own chat agent can close both gaps in public.

## What to build

1. **Home:** one-line positioning, the four case studies, links.
2. **Case study pages:** problem, architecture diagram, what failed, cost, how it was measured.
3. **Ask agent:** chat grounded only in the case studies and ADRs, with citations and an honest "I haven't written about that".
4. **`/evals` page:** the agent's test suite and pass rate, with tests blocking deploys.
5. **Writing:** start with posts that already have material, such as the admission guard, MCP OAuth for connectors, and Sandcastle loops.
6. **Agent surface:** `llms.txt`, JSON-LD, and optionally a small personal MCP endpoint.

## Boilerplate options

Stars, licenses and last push were checked against GitHub on 2026-10-04.

| Template | Stars | License | Last push | Fit |
|---|---|---|---|---|
| `magicuidesign/portfolio` | 1.5k | MIT | Jan 2026 | Next.js 14 + shadcn + Magic UI; one resume config file. **Pick for the shell.** |
| `santifer/cv-santiago` | 850 | none | Oct 2026 | React 19 + Vite + Claude chat with hybrid RAG, 71 evals, guardrails, Langfuse. Reference only: with no license, don't fork it. |
| `leerob/next-mdx-blog` | 7.6k | none | Sep 2026 | Minimal Next.js + MDX; good if writing leads, but no license. |
| `satnaing/astro-paper` | 5.1k | MIT | Oct 2026 | Best maintained writing-first option; Astro, so the chat needs an island or separate endpoint. |
| `jktrn/astro-erudite` | 867 | MIT | Jul 2026 | Astro blog plus projects section. |
| `mldangelo/personal-site` | 1.7k | MIT | Oct 2026 | Static export, resume-style. |

The Magic UI template is on Next.js 14, so expect an upgrade pass. The alternative is to stay on TanStack Start (used in Next1, Renderia and FitLab), treat these templates as design references and build the shell by hand; no strong TanStack Start portfolio template turned up.

## Things to handle carefully

- **Lovable-built sites** (prehab, nutrition, physio, rehab method, landing): present them as products directed, not code written by hand.
- **Fourth:** describe it only at a high level.
- **Next1:** the repo has one other contributor and mentions "owner decisions", so check what can be shown publicly.
- **Token files:** `omnibody-gtm-meta-scripts` holds plaintext token files and is not a git repo; keep it out of anything published.

## Open decisions

- Magic UI base or TanStack Start built by hand.
- Whether to ship a personal MCP endpoint.

## Sources

- [Ultimate guide to AI engineering portfolios](https://www.dataexpert.io/blog/ultimate-guide-ai-engineering-portfolios)
- [Hiring AI engineers 2026](https://www.callmissed.com/blog/hiring-ai-engineers-2026)
- [What I look for when hiring AI engineers](https://www.louisbouchard.ai/what-i-look-for-when-hiring-ai-engineers/)
- [What hiring managers actually look for in AI engineers](https://gauntletai.com/night-school/what-hiring-managers-actually-look-for-in-ai-engineers)
- [cv-santiago write-up](https://prompts.brightcoding.dev/blog/santifercv-santiago-production-grade-ai-portfolio-with-agentic-rag)
- [llms.txt guide](https://llmpulse.ai/blog/llms-txt-guide/)
- [Twinfolio](https://www.producthunt.com/products/twinfolio)
- [Best Next.js personal website templates](https://designrevision.com/blog/best-nextjs-personal-website-templates.md)
- [AstroPaper](https://gittrend.io/repo/satnaing/astro-paper)
- [astro-erudite](https://gittrend.io/repo/jktrn/astro-erudite)
