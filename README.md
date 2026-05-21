# Pathogen Surveillance

## Overview

This project explored a scalable workflow for connecting large-scale pathogen sequence search results with environmental and geographic metadata analysis.

The primary objective was not full genomic characterization, but rather the development of a pipeline capable of:
- querying large sequencing indexes,
- retrieving matched accessions,
- linking those matches to metadata repositories,
- filtering usable metadata fields,
- and generating spatial representations of the resulting data.

The workflow focused heavily on metadata integration, normalization, and downstream geographic interpretation.

---

## Core Workflow

The overall pipeline followed a multi-stage process:

1. Select a pathogen, marker, or genomic target.
2. Query large-scale sequence indexing/search tools such as MetaGraph.
3. Retrieve matching accessions from search results.
4. Cross-reference accessions against associated metadata repositories.
5. Extract usable attributes such as:
   - geographic coordinates,
   - environmental source information,
   - host metadata,
   - collection details,
   - and sample descriptors.
6. Normalize inconsistent metadata formats.
7. Filter incomplete or unusable records.
8. Map resulting geographic data for downstream analysis and visualization.

This workflow enabled the transition from raw sequence matches to geographically contextualized datasets.

---

## Metadata Processing

A significant portion of the project involved handling real-world metadata inconsistencies across biological repositories.

Examples of issues encountered included:
- malformed latitude/longitude values,
- missing geographic fields,
- inconsistent environmental descriptors,
- duplicated accession relationships,
- variable formatting standards,
- and incomplete sample annotations.

Custom parsing and filtering workflows were developed to identify usable records and prepare them for geospatial analysis.

---

## Spatial Mapping & Interpretation

After metadata extraction and cleanup, geographic information was transformed into map-compatible datasets for visualization and exploratory analysis.

The visualization below represents environmental detections associated with *Bacillus anthracis* pXO1-related sequence signatures across globally distributed samples.

![Anthrax Map Preview](images/anthrax_preview.png)

Each plotted point represents a metadata-linked sample location where sequence search results produced measurable matches against the target reference.

The visualization incorporates a **k-mer coverage fraction** metric, which represents the proportion of target k-mers detected within a given sample.

### Why k-mer Coverage Matters

K-mer coverage provides a lightweight but powerful method for estimating how strongly a sample matches a target sequence without requiring full genome alignment.

Higher coverage fractions generally indicate:
- stronger sequence similarity,
- greater representation of the target signal,
- or higher confidence that related genomic material exists within the sample.

Lower values may indicate:
- weak environmental traces,
- fragmented detections,
- low-abundance signal,
- or partial sequence overlap.

This becomes especially important in large-scale environmental screening workflows, where millions of samples may need to be rapidly searched and ranked before deeper analysis is performed.

---

## Example Interpretation

In the example visualization:
- larger and brighter markers correspond to stronger sequence detection signals,
- weaker signals appear as smaller/darker detections,
- and geographic clustering may indicate regions containing environmentally related samples or repositories with enriched matching data.

The figure demonstrates how large-scale sequence search outputs can be transformed into geographically interpretable datasets capable of supporting exploratory pathogen surveillance workflows.

Importantly, the visualization does **not** imply confirmed outbreaks or active environmental presence. Instead, it represents metadata-linked sequence detections derived from indexed biological datasets.

---

## Technical Focus Areas

The project primarily centered around:
- large-scale sequence search workflows,
- metadata parsing and normalization,
- accession relationship handling,
- geospatial data extraction,
- coordinate validation,
- environmental metadata interpretation,
- and downstream mapping integration.

The work combined concepts from:
- bioinformatics,
- data engineering,
- metadata systems,
- and geospatial analysis.

---

## Repository Contents

```text
README.md
anthrax_map.html
images/
└── anthrax_preview.png
