# Excalidraw Video Diagrams

Professional diagrams designed for video content. Fork of [excalidraw-skill](https://github.com/robonuggets/excalidraw-skill) by RoboNuggets, enhanced by AI Injection.

Turn text descriptions into video-ready diagrams on a live Excalidraw canvas. Your AI agent draws, screenshots its own work, and iterates until it looks right. Optimized for 1080p/4K video overlays.

## What You Get

- **15 visual techniques** -- everything in the original plus 5 new diagram types
- **Video-ready presets** -- 1080p and 4K safe zones, title cards, scene overlays
- **Animation frames workflow** -- build diagrams in stages, export frame sequences for video
- **Dark theme first** -- designed for video overlays on dark backgrounds
- **Self-correcting diagrams** -- the agent sees its own canvas and fixes issues automatically
- **Quality checklist** -- catches truncation, overlap, and bad arrows before export
- **Multiple exports** -- PNG, SVG, .excalidraw (re-editable), or shareable URL

## Improvements Over Original

| Feature | Original | This Fork |
|---------|----------|-----------|
| Diagram types | Flowcharts, architecture | + Mind maps, timelines, comparisons, funnels, cycles |
| Video support | None | 1080p/4K presets, scene overlays, lower-third spacing |
| Animation | Static only | Frame-by-frame build-up workflow for video |
| Theme | Light + dark | Dark-first design for video content |
| Text sizing | 14px minimum | 18px body / 32px title minimum (readable on phone) |
| Stroke width | 1px default | 2px minimum (visible on video) |

## New Diagram Types

| # | Type | Description |
|---|------|-------------|
| 11 | Mind Map | Central topic with radiating branches, 2 levels deep |
| 12 | Timeline | Horizontal with date markers and event cards |
| 13 | Comparison/VS | Two-column layout with divider, pros vs cons |
| 14 | Funnel | Wide top tapering to narrow bottom, 4 stages |
| 15 | Cycle | Nodes in a circle with connecting arrows |

## Original 10 Techniques

| # | Technique | What It Does |
|---|-----------|-------------|
| 1 | Layered Glow | Stacked rectangles at decreasing opacity for depth |
| 2 | Color-Coded Zones | Background rectangles grouping related elements |
| 3 | Bound Arrows | Arrows that snap to shapes and auto-route |
| 4 | Line Style Meaning | Solid = sync, dashed = async, dotted = optional |
| 5 | Diamond Decisions | Flowchart branching with Yes/No paths |
| 6 | Mixed Shapes | Ellipse = actor, rectangle = service, diamond = decision |
| 7 | Font Hierarchy | 28px title, 20px section, 16px body, 14px notes |
| 8 | Semantic Colors | 7-color palette with consistent meaning |
| 9 | Mermaid Conversion | Convert Mermaid syntax to editable Excalidraw |
| 10 | Screenshot Loop | Agent sees and fixes its own work |

## Prerequisites

You need the Excalidraw MCP server installed and running.

### 1. Clone and build the MCP server

```bash
git clone https://github.com/yctimlin/mcp_excalidraw && cd mcp_excalidraw
npm ci && npm run build
```

### 2. Add to Claude Code

```bash
claude mcp add excalidraw -s user \
  -e EXPRESS_SERVER_URL=http://localhost:3000 \
  -- node /absolute/path/to/mcp_excalidraw/dist/index.js
```

Replace `/absolute/path/to/` with wherever you cloned the repo.

### 3. Start the canvas

```bash
cd /path/to/mcp_excalidraw
PORT=3000 npm run canvas
```

Open `http://localhost:3000` in your browser to see the live canvas.

## Install the Skill

```bash
claude skill add --url https://raw.githubusercontent.com/robertmilven/excalidraw-video-diagrams/master/.claude/skills/excalidraw/SKILL.md
```

Or manually: copy `.claude/skills/excalidraw/SKILL.md` into your project's `.claude/skills/excalidraw/` folder.

## Try It

Once the MCP server is running and the skill is installed:

- "Draw an architecture diagram for a web app with a load balancer, two servers, and a database"
- "Create a mind map about AI content creation tools"
- "Make a timeline showing our product roadmap for 2025"
- "Build a comparison diagram: monolith vs microservices"
- "Create a funnel diagram for our sales pipeline"
- "Make a video-ready flowchart showing user authentication, export as animation frames"

## Known Limitations

- **Images**: Can't be added via MCP -- drag them into the browser manually
- **Freedraw**: Draw freehand in the browser, not via MCP
- **SVG import**: Use the browser's native paste feature

## Credits

- Original skill by [RoboNuggets](https://github.com/robonuggets/excalidraw-skill)
- Video features and new diagram types by [AI Injection](https://github.com/robertmilven)

## License

MIT
