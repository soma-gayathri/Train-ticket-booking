# Train Finder

Single-page app: enter a source and destination station and see the trains that run between them.

## Data model (3 tables)
- `trains` (train_id, name)
- `stations` (station_id, name)
- `train_stops` (train_id, station_id, stop_order, arr)

`data/seed.json` holds the sample rows (illustrative timings only; confirm on IRCTC/NTES).

## Note
`index.html` reads the tables through the Claude artifact database (`claude.use("db")`),
so it only works when hosted as a Claude artifact. To run it elsewhere, replace the
`load()` function with `fetch("data/seed.json")` or a call to your own backend.
