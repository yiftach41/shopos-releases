# shopos-releases

The ShopOS update channel. Client stores poll `manifest.json` in this repo and
install the version it names — this is not a source repository, and nothing here
is edited by hand.

- `manifest.json` — the published version of each package plus its download URL
  and `sha256`. Written by `tools/publish.sh` in the ShopOS monorepo.
- **Releases** — one per package version (`core-<x.y.z>`, `theme-<x.y.z>`), each
  carrying the built zip and its `.sha256` sidecar as assets.

The zips are integrity-checked against the sidecar by the updater before
install. Publishing happens once per version; a version is never re-uploaded.
