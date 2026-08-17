# Cape Town Informal Settlements: Housing & Ward-Level Analysis

A spatial analysis of informal settlements in Cape Town, exploring how these communities are distributed across the city's ward boundaries. This project extends the theoretical framework from my MDSSB-APP-01 academic paper on datafication and the visibility of informality in Cape Town into a hands-on, technical analysis.

## Author

Uyazi Dube — MSc Data Science for Society and Business, Constructor University Bremen. Background in Human Settlements (BSocSc) with a focus on housing policy, bridging urban planning and data science.
## Project Overview

**Objective:** Map known informal settlements against Cape Town's ward boundaries to explore spatial distribution patterns, and connect the findings to broader questions about data visibility and informality in urban policy.

**Key question:** Where are Cape Town's informal settlements located relative to administrative ward boundaries, and what does the process of finding this data reveal about the "datafication" of informal versus formal urban spaces?

## Data Sources

| Source | Description | Access method |
|---|---|---|
| City of Cape Town Ward Boundaries | Official ward boundary polygons | ArcGIS Hub REST API (GeoJSON) |
| Curated Informal Settlements Dataset | 11 well-documented settlements with coordinates, compiled from public records, news reporting, and academic literature | Manually compiled (see Limitations) |

**Settlements included:** Khayelitsha, Dunoon, Imizamo Yethu, Marikana, Kosovo, Nyanga, Philippi, Delft, Mfuleni, QQ Section, Joe Slovo

## Methodology

1. Pulled Cape Town ward boundary data via the City's ArcGIS Hub REST API
2. Compiled a curated dataset of well-documented informal settlements with coordinates
3. Performed a spatial join to determine which ward each settlement falls within
4. Aggregated and visualized settlement counts per ward
5. Produced a written analysis connecting findings to the datafication framework

## Key Findings

- All 11 settlements were successfully matched to a ward with zero unmatched records.
- 10 of 11 wards contain exactly one settlement each; Ward 36 contains two (Marikana and Kosovo).
- Settlements are geographically dispersed across the city rather than clustered in one area.

Full write-up in [`report/policy_brief.md`](report/policy_brief.md) or the final section of the notebook.

## Data Sources & Limitations

This project originally aimed to use an official, comprehensive informal settlements shapefile from the City of Cape Town's open data ecosystem (via openAfrica). Repeated access attempts, including direct download and scripted requests with browser headers, returned persistent `403 Forbidden` errors, suggesting bot protection on that platform.

Given project timeline constraints, the approach pivoted to a smaller, manually curated dataset of well-documented informal settlements, combined with the City of Cape Town's ward boundaries (successfully accessed via their ArcGIS Hub REST API).

This is not an exhaustive dataset. Cape Town has considerably more informal settlements than are represented here, with estimates running into the hundreds. This project describes where these known settlements sit relative to ward boundaries, not the full scale or distribution of informality citywide. No population, service-access, or settlement-size data is included in this iteration.

## Tech Stack

- Python (pandas, GeoPandas, Shapely)
- Matplotlib for visualization
- Google Colab

## Repository Structure
