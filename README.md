# Evaluating the Maintainability of Apache Hudi

An empirical study applying the GQM framework to evaluate the maintainability of [Apache Hudi](https://hudi.apache.org/), an open-source Java data lake platform, across five releases (0.13.0 – 1.1.0).

## Study Overview

We analysed 14 Maven modules across five releases using three tools — CK, MetricsReloaded, and SonarQube — collecting metrics covering five internal structural attributes:

- **Size** — LOC, NCLOC, NOM, NOF
- **Coupling** — CBO, FanIn, FanOut
- **Cohesion** — LCOM*, ICH
- **Complexity** — WMC, Cognitive Complexity
- **Understandability** — DIT, NOC, NOM/class, Comment Lines Density

Modules are ranked by SQALE Debt Ratio and cross-release trends are analysed for each attribute.

## Key Findings

- `hudi-utilities` (1.37%), `hudi-cli` (1.23%), and `hudi-sync` (1.23%) carry the highest maintenance burden relative to their size
- LOC and Cognitive Complexity are very strongly correlated (Spearman ρ = 0.965, p < 0.001)
- The most frequently changed modules carry the least debt; less active modules accumulate more
- No single metric is sufficient — each top-ranked module reached high debt through a different structural route

## Report

The full report is available in [`Group8_Measurement_Project_Report.pdf`](Group8_Measurement_Project_Report.pdf).

## Tools

- [CK 0.7.0](https://github.com/mauricioaniche/ck) — class-level OO metrics
- MetricsReloaded — NCLOC
- SonarQube — Cognitive Complexity, Comment Density, SQALE Debt Ratio
- [Torko](https://github.com/vector94/torko) — custom metric aggregation and visualisation platform built for this study

