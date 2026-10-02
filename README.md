# Starlight.Maps
Repository for Map renderers for Map Viewer.

## Projects

`projects.json` lists every project shown in the Map Viewer. Each project is a collapsible category in the sidebar:

```json
[
    { "id": "starlight", "name": "Starlight", "index": "index.json" },
    { "id": "myproject", "name": "My Project", "index": "https://raw.githubusercontent.com/me/MyProject.Maps/main/index.json" }
]
```

- `id` - goes into viewer links (`/maps?project=myproject&map=box`), keep it short and stable.
- `name` - category title.
- `index` - URL of the project's `index.json`, either absolute or relative to `projects.json`.

To add your project, host your rendered maps anywhere publicly reachable (a GitHub repo works) and open a PR adding an entry here.

## index.json

```json
[
    { "mapId": "box", "displayName": "Box Station", "url": "maps/box/map.json" },
    { "mapId": "arrivals", "displayName": "Arrivals Shuttle", "url": "maps/arrivals/map.json", "type": "shuttle" }
]
```

- `type` - `station` (default) or `shuttle`; shuttles are listed on their own tab.
- `url` - absolute, or relative to the `index.json` itself.

The viewer caches the catalog for 5 minutes, so changes show up with a small delay.
