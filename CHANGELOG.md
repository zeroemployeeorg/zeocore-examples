# Changelog

All notable changes to this repository are recorded here, newest first. The format follows
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/). This repository has no releases or tags yet,
so entries are grouped by month.

## Status (as of 20 November 2026)

- **What it is:** a set of small, runnable example applications built on
  [zeocore](https://github.com/zeroemployeeorg/zeocore), meant to teach how to build a real application on it and to
  test zeocore against realistic use. It is not a production tool.
- **How alive:** maintained, at a slow pace. Last meaningful change: 1 September 2026. No releases yet.
- **Works today:** three example apps, each its own installable package with a demo that runs on dummy data with no
  credentials: `data_cleaning` (CSV contact and company cleaning), `metrics_tracker` (weekly business metrics with
  validation) and `doc_to_bluesky` (publish a Google Doc's text to Bluesky). An optional Google Drive demo and a
  Google Doc to Bluesky demo need real accounts; `SETUP.md` walks through them.
- **Known not to work yet:** the app dependencies were last updated when zeocore was much older (`zeocore>=0.1.0`
  and `>=0.6.0`), and have not been re-checked against current zeocore. `.env.example` still lists storage
  placeholders (a hosted database) that no app uses. There is no automated test suite yet.
- **Check it yourself:** run `make help`, then `make verify` once the Makefile lands; until then, follow the
  "Install and run" section of the README.

## [Unreleased]

### Added
- `CHANGELOG.md`, this file.

## 2026-09

### Added
- `doc_to_bluesky`: an example app that reads the text of a Google Doc and posts it to Bluesky, with a working link
  inside the post. It includes runnable instructions.

### Fixed
- The `doc_to_bluesky` demo printed an internal object representation for the capability status; it now prints the
  readable value.
- The README's Google Docs credentials example showed the wrong constructor arguments, which would have misled readers
  following it. It now matches the real code.

## 2026-08

### Added
- First commit: README, `.gitignore` and an `.env.example` that documents the shape of the settings a live session
  would need. The demos need none of them.
- `data_cleaning`: a rebuild of a public B2B contact and company data-cleaning course project as typed zeocore tools:
  two pipeline tools (clean contacts, clean accounts) and three small utilities (clean an email address, normalize a
  country name, extract a domain).
- `metrics_tracker`: a rebuild of a public weekly business-metrics tracker as one typed tool with validated input.
- `data_cleaning`: an optional tool that downloads a CSV from a real Google Drive file and feeds it into the same
  cleaning tools, plus a beginner `SETUP.md` that walks through the Google Cloud sign-in setup.

### Fixed
- `metrics_tracker` closes a real bug in the project it rebuilds: the original divided by zero when no hours were
  entered and accepted more automated hours than total hours. Both inputs are now validated.
