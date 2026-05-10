# Migrating Off Dropbox: Beyond Dotfiles

*2026-05-07 16:11 PDT*

Companion compendium for the blog post 'Migrating Off Dropbox:
Beyond Dotfiles', a sequel to post 24 ('Creating a GitHub Dotfiles
Repository').

## Topic

Post 24 establishes a portable dotfiles repository. This post
extends the same goal to the rest of a single-user research
workflow: project content, backup-pipeline source paths, and the
append-only history files that Dropbox handles particularly badly.
The body frames the problem as three layers and walks through
trade-offs for each.

## Deliverable

The post centres on a decision worksheet that walks a reader
through inventory, mechanism selection, migration order, and
verification:

- `docs/migration-decision-worksheet.qmd`

The worksheet is generic; it does not assume any particular project
structure or sync mechanism. Fill it in for your own setup and the
migration becomes a series of small, audited moves.

## Body

The blog post body is at:

- `analysis/report/index.qmd`

The root-level `index.qmd` is a symlink to the report file; Quarto
renders either path.

## Build Targets

Standard zzcollab Makefile targets apply:

- `make r`               — start the analysis container
- `make build`           — build the Docker image
- `make render`          — render the blog post to HTML
- `make check-renv`      — validate package dependencies
- `make test`            — run the test suite (none defined for
                           this post)
- `make clean`           — remove rendered artefacts

## Directory Tree

```
migrating-off-dropbox/
├── analysis/
│   ├── report/
│   │   └── index.qmd                     <- the blog post body
│   ├── media/
│   │   └── images/                       <- hero + ambiance images
│   └── configs/                          <- empty (no scripts in
│                                            this post)
├── docs/
│   ├── README.md                         <- this file
│   ├── migration-decision-worksheet.qmd  <- the deliverable
│   ├── DATA_WORKFLOW_GUIDE.md            <- generic; kept
│   ├── ZZCOLLAB_BLOG_SETUP.md            <- generic; kept
│   └── ZZCOLLAB_USER_GUIDE.md            <- generic; kept
├── DESCRIPTION                           <- compendium metadata
├── Dockerfile                            <- analysis container
├── Makefile                              <- standard zzcollab
│                                            targets
├── NAMESPACE                             <- empty (no R/ exports)
├── renv.lock                             <- pinned R packages
└── zzcollab.yaml                         <- compendium config
```

## See Also

- Post 24, the prerequisite: [Creating a GitHub Dotfiles Repository](https://focusonr.org/posts/24-setupdotfilesongithub/)
- Post 20, the backup foundations: [Setting Up a Comprehensive Research Backup System on macOS](https://focusonr.org/posts/20-researchbackupsystem/)
