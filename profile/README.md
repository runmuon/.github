# Muon

**Open-source product analytics that explain what changed, why it changed and who was affected.**

Muon is a self-hostable analytics stack for teams that want more than traffic
charts. It combines Umami-compatible web analytics, product events, funnels,
browser health and SDKs in a fast Rust + PostgreSQL core.

## Start Here

| Repository | What it gives you |
| --- | --- |
| [runmuon/muon](https://github.com/runmuon/muon) | Full analytics stack: Rust API, React dashboard, tracker, Docker Compose and benchmarks. |
| [runmuon/tracker](https://github.com/runmuon/tracker) | Dependency-free browser tracker with SPA pageviews, custom events and optional JS error capture. |
| [runmuon/muon-js](https://github.com/runmuon/muon-js) | Throw-safe Node.js SDK with persistent offline queue and process error capture. |
| [runmuon/muon-swift](https://github.com/runmuon/muon-swift) | Swift SDK for iOS, macOS, tvOS and watchOS with offline queue and crash handoff. |
| [runmuon/web](https://github.com/runmuon/web) | Static marketing and documentation site for muon.run. |

## Why Teams Use Muon

- **Own your product data.** Self-host the pipeline and keep raw events inside
  your infrastructure.
- **Migrate from Umami without a rewrite.** Muon accepts Umami-compatible
  tracking payloads and exposes a familiar browser API.
- **Connect behavior and health.** Track pageviews, custom events, funnels and
  distilled frontend errors in one product timeline.
- **Low operational weight.** The Rust backend is small, fast to start and built
  around PostgreSQL first.
- **SDKs that do no harm.** Browser, Node and Swift clients are designed to fail
  quietly, bound queues and never crash the host app.

## Quick Start

```bash
git clone https://github.com/runmuon/muon.git
cd muon
npm --prefix tracker ci
npm --prefix tracker run build
docker compose up --build
```

Open the dashboard at `http://localhost:3000`.

## Track an Event

```html
<script
  defer
  src="https://analytics.example.com/tracker.js"
  data-website-id="YOUR_PROJECT_ID"
  data-host-url="https://analytics.example.com"
  data-track-errors="true"
></script>
```

```js
muon.track("signup_completed", { plan: "pro" });
muon.identify("user_123");
muon.setRelease("1.8.4");
```

## License

Muon repositories are published under MIT unless a repository states otherwise.
