# Tradify

Local-first, educational AI stock-research app: Next.js 16 · SQLite (`node:sqlite`) · Yahoo Finance · LangChain agent via OpenRouter · optional Tavily web search. It never gives buy/sell recommendations.

## Run it

```bash
npm install
cp .env.example .env.local   # set SESSION_SECRET; add OPENROUTER_API_KEY / TAVILY_API_KEY if you have them
npm run dev                  # http://localhost:3000
```

Requires Node 22+. Without `OPENROUTER_API_KEY` the app returns a deterministic, data-backed analysis. Without `TAVILY_API_KEY` the `web_search` tool is disabled.

```bash
npm run lint && npm test && npm run build
```

Docs: [`docs/architecture.md`](docs/architecture.md), [`docs/build-guide.md`](docs/build-guide.md).

## Deploy note
SQLite is not durable on Vercel's serverless filesystem. Swap `src/lib/db.ts` for hosted Postgres/Turso before real multi-user use.
