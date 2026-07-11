# OpenRail Tycoon

A single-file browser game: buy real German ICE train lines pulled live from
OpenStreetMap and grow a rail empire.

Open `index.html` in a browser — no build step, no server needed.

## How it plays

- All ICE route relations are fetched from the Overpass API (station-to-station
  geometry, grouped by line number). **Available lines are drawn red, owned
  lines green.**
- The sidebar overview shows **routes bought / total**, trains, carts, and the
  current demand multiplier.
- Every owned route starts with 1 train carrying 1 cart. You can **buy extra
  trains per line and extra carts per train** — each repeat purchase costs
  **10× the previous one**.
- Cities **grow at 20× speed** and drive passenger demand (and your income).
- The **history panel timestamps every event**.
- OSM data updates (initial load, the ⟳ button, and a scheduled refresh every
  30 minutes) **block the page with an overlay and re-render when finished**.
- Progress is saved to `localStorage`; the Reset button wipes the save.

If Overpass is unreachable, the game falls back to cached data or a small set
of built-in lines so it stays playable offline.
