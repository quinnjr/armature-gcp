# Changelog — `armature-gcp`

All notable changes to this crate will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this crate adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

Earlier changes are recorded in the workspace [`CHANGELOG.md`](../CHANGELOG.md).

## [Unreleased]

### Security

- **Breaking:** the `spanner` feature now uses `gcloud-spanner` 1.8 instead of `google-cloud-spanner` 0.33. The old crate depended on `google-cloud-auth` 0.17, which pinned `jsonwebtoken` 9.3.1 (CVE-2026-25537); `gcloud-spanner` uses `gcloud-auth` 1.x → `jsonwebtoken` 10.x, the same stack `bigquery` already uses. The re-export moves from `armature_gcp::google_cloud_spanner` to `armature_gcp::gcloud_spanner`, and `GcpServices::spanner()` returns `gcloud_spanner::client::Client`. Migration: rename the import path; the client API is the same (same upstream author, renamed crate).

## [0.2.2] - 2026-09-15

### Changed

- Dependencies bumped to their latest releases: `google-cloud-auth` 1.14 → 1.16, `google-cloud-pubsub` 1.1 → 1.4, `google-cloud-storage` 1.15 → 1.18, `tokio` 1.52 → 1.53, `tokio` 1.52 → 1.53.

