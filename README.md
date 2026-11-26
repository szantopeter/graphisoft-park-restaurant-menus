# Graphisoft Park Restaurant Menus

Daily menu aggregator for restaurants near the Budapest Graphisoft Park office.
Data is parsed and updated each day by an n8n workflow, which commits `daily-menu.json` to this repo.
GitHub Pages serves `index.html`, which reads that file at runtime.

## Local development

```bash
cd ~/dev/src/graphisoft-park-restaurant-menus
python3 -m http.server 8765
```

Then open http://localhost:8765 in your browser.

> A plain `open index.html` won't work — the page fetches `daily-menu.json` via `fetch()`, which browsers block on `file://` URLs. You need a local HTTP server.
