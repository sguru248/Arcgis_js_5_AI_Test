# ArcGIS Agentic AI Map

A single-page application using **ArcGIS Maps SDK for JavaScript v5.0** AI components (beta) to enable natural language interaction with a web map.

## Features

- **AI Assistant** — Chat interface for interacting with your web map using natural language
- **3 Built-in Agents**:
  - **Navigation Agent** — "Where" questions: navigates/zooms to locations (e.g., "Go to New York")
  - **Data Exploration Agent** — "What" questions: queries, filters, statistics (e.g., "How many features?")
  - **Help Agent** — Contextual guidance about layers and capabilities (e.g., "What layers are in this map?")
- **Map Widgets** — Zoom, Home, Search, Legend, Scale Bar, Basemap Toggle (all expandable, no overlap)
- **Dynamic Suggested Prompts** — Auto-generated based on actual layer names in the map

## Tech Stack

- ArcGIS Maps SDK for JavaScript 5.0 (CDN)
- ArcGIS AI Components (beta)
- Calcite Design System Components
- No build tools required — single `index.html` file

## Getting Started

### Prerequisites

1. **ArcGIS Online account** with a named user license
2. **AI Assistants enabled** in your ArcGIS Online org settings (admin task)
3. **AI vector embeddings generated** on the web map item:
   - Go to your web map item page in ArcGIS Online
   - Settings → "Manage AI vector embeddings" → Generate
4. Feature layers should have meaningful names, field aliases, and descriptions

### Run Locally

Serve via HTTP (file:// protocol won't work):

```bash
npx http-server -p 8080 -c-1 -o
```

Then open `http://localhost:8080` in your browser.

### Usage

1. The map loads with your web map data and all widgets
2. The AI Assistant panel appears on the right
3. Sign in with ArcGIS Online credentials when prompted
4. Ask questions in natural language or click suggested prompts

### Example Queries

| Agent | Example |
|-------|---------|
| Navigation | "Go to San Francisco", "Zoom in" |
| Data Exploration | "How many features are there?", "What's the average?" |
| Help | "What layers are in this map?", "What can I ask?" |

## Configuration

To use your own web map, change the `item-id` attribute on the `<arcgis-map>` element:

```html
<arcgis-map id="main-map" item-id="YOUR_WEB_MAP_ID">
```

## Notes

- AI components are in **beta** — results may be inaccurate
- Only **Feature Layers** are supported by agents (other layer types display but can't be queried)
- Requires an active internet connection for ArcGIS Online services
