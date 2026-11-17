# OfflineNav map packages

Public, static distribution of regional `.nvmpkg` packages for the OfflineNav Android app.
The application code remains in a separate private repository.

## What this repository contains

- `catalog.json` — the machine-readable region catalog downloaded by the app.
- GitHub Release assets — immutable `.nvmpkg` packages and checksums.
- `LICENSE-OSM.txt` — data license/attribution.

No user data, telemetry or account data is stored here.

## Catalog URL

The app reads the catalog from the **latest** release asset:

```
https://github.com/vasil1729/offline-navigation-packages/releases/latest/download/catalog.json
```

Every release must attach an updated `catalog.json` plus new package assets. Package URLs in the
catalog point at the immutable versioned release tag that contains them.

## Licenses

Map data © OpenStreetMap contributors, licensed under ODbL 1.0.
See `LICENSE-OSM.txt`. Packages include their own attribution and license files.

## Updating

1. Build a package with the OfflineNav map pipeline.
2. Add/refresh its entry in `catalog.json` with byte size and SHA-256.
3. Create a new release tag, attach the package, its `.sha256`, and the updated `catalog.json`.
4. Verify the release assets download anonymously with `curl -L`.
