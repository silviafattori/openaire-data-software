# Tracking Research Data and Software Using Open Sources

**Proposal for VU Open Science Day poster session – November 2025**  
**Team Research Intelligence, University Library, VU Amsterdam**

---

## Overview

Open science encourages researchers to share a broad range of outputs, including research data and software. Yet these contributions often receive little recognition in research assessment. Part of the challenge lies not only in existing reward structures but also in the limited availability and quality of metadata describing these outputs.

Open infrastructures like **OpenAIRE** offer opportunities for more inclusive evaluation by indexing these outputs and providing the possibility to explore links between research products. Assessing the coverage, quality, and usefulness of metadata is crucial to inform discussions on recognition and reward systems in open science.

This project explores the potential of OpenAIRE to track research data and software authored by VU researchers, focusing on metadata coverage, quality, and linking between research products.

---

## Data sources

[OpenAIRE Graph API](https://graph.openaire.eu/docs/apis/graph-api/) to query:

- Research products (datasets, software) and corresponding metadata

- Relationships between research products.

---

## Methodology

1. **Data Retrieval**
- Filter by organization ROR ID (https://ror.org/008xxew50) to restrict to VU outputs.
- Retrieve all datasets and software published by VU from 2020–2024 via the OpenAIRE Graph API.

2. **Data Normalization and Duplicate Detection**
- Normalize titles (strip whitespace, lowercase) and exclude irrelevant entries (e.g., figure-specific titles).
- Identify duplicate titles and collect relevant metadata (authors, publisher, date, ID).
- Standardize authors and compare across duplicates.

3. **Metadata Completeness Assessment**
- Inspect missing values for key fields (country, subject, PID).

4. **Links Analysis**
- Extract persistent identifiers (DOI, Handle, PMID, ARK, ArXiv, URL) per research product.
- Query the OpenAIRE links API to retrieve relationships (target or source).
- Process results in batches and combine into a single CSV.
- Compute summary statistics: average links per PID, percentage with at least one link, relationship types, source types.

5. **Exploratory Analysis**
- Summarize: Open Access labels, publication years, hosting sources, topics, citation counts.

---

## Usage

1. Clone this repository: *git clone https://github.com/silviafattori/openaire-data-software.git*
2. Install dependencies: *pip install -r requirements.txt*
3. Run notebook *Dataset_Software_OpenAIRE.ipynb*

---

## License

This project is released under the MIT License. You are free to use, modify, and distribute the code and data, provided that proper attribution is given to the original authors.

