# Psychometrics

This repository contains assignments for **Psychometrics**.

Rendered: <https://thatmariia.github.io/psychometrics/>

## Setup

Package versions are pinned with [renv](https://rstudio.github.io/renv/):

```r
renv::restore()
```

## Assignments

| id | Title | Source | Hand-in |
|----|-------|--------|---------|
| `01-ctt` | Assignment 1: Classical Test Theory | [Rmd](assignments/01-ctt/01-ctt.Rmd) | [HTML](output/01-ctt.html) |

## Starting a new assignment

Build the scaffold from the questions in html:

```bash
Rscript scripts/import-assignment.R <path> <id>
```

That writes `assignments/<id>/<id>.Rmd` with figures extracted into
`figures/`.

Datasets live in `data/ass<n>/`; from inside an assignment that is
`../../data/ass<n>/<file>.csv`.

Start a blank assignment:

```bash
Rscript scripts/new-assignment.R <id> <title>
```

## Rendering

```bash
Rscript scripts/render.R <id>
Rscript scripts/render.R  # renders all assignments
```

The results are written in `output/`.

An assignment whose YAML header says

```yaml
render_locally: false
```

is skipped - it is knitted elsewhere (like on a course server that
can reach a database a local machine can't), and the committed HTML in
`output/` is the real hand-in. Both `render.R` and the GitHub Actions
workflow respect the flag.
