# applicator

Daily job digest support repo.

- `.github/workflows/fetch-jobs.yml` runs on GitHub's runners (unrestricted internet) daily at 04:00 UTC and commits fresh job listings from RemoteOK, Arbeitnow, and Remotive into `data/`.
- A separate scheduled Claude Code routine reads `data/*.json` from this repo daily at 05:05 UTC, matches listings against Yusuf's skills/resume, emails a shortlist, and records what's already been sent in `seen_jobs.json` to avoid duplicates.
- No application is ever auto-submitted; this only produces a shortlist for manual review.
