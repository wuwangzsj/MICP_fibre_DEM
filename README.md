# MICP_fibre_DEM

**Model code and data for analysing cementation, fibre load transfer and skeleton damage in bio-cemented calcareous sand.**

This repository supports three-dimensional discrete element modelling of fibre-assisted microbially induced carbonate precipitation (MICP) treatment of calcareous sand under unconfined compression.

The study uses paired numerical cases sharing the same initial sand skeleton to examine effective bond area, radial cementation distribution and sand–fibre interface bonding. Random and near-horizontal fibre assemblies are analysed to investigate the relationship between fibre tension and local skeleton damage.

## Repository contents

Code and data are being added progressively. The release is organized into three components.

### Model code

PFC3D 6.0 source modules document:

- Specimen generation and fibre placement.
- Sand–sand, sand–fibre and fibre–fibre contact properties.
- Effective bond-area allocation and radial cementation configurations.
- Platen loading and numerical recording.
- Branching at 0.2% axial strain to maintain surviving sand–fibre interface bonds.

### Post-processing code

Python scripts provide:

- **First-peak identification** using stress-drop criteria.
- **Sectional load decomposition** into sand and fibre-related contributions.
- **Same-bond tracking** across paired cases, including regional damage and common or case-specific failures.
- **Fibre-force analysis**, including chainwise maximum absolute axial force, tensile-segment fractions, regional tensile-force shares and inclination statistics.
- **Debonding-interval analysis** linking interface failure to force changes within the same fibre chain.

### Data and supplementary results

The data package contains archived numerical exports and processed CSV tables, including:

- Stress–strain histories and quality indicators.
- Initial particle geometry and bond identities.
- Bond-failure events and selected particle/contact states.
- Figure source data and numerical tables.
- Experimental UCS and calcium carbonate content summaries, with original source attribution.
- Verification examples for key numerical results.

A figure–table–file correspondence table is included in the data package.

## Directory structure

```text
MICP_fibre_DEM/
├── README.md
├── LICENSE
├── COMPLETENESS.md
├── requirements.txt
├── model/
│   ├── 01_specimen/
│   ├── 02_bonds/
│   ├── 03_loading/
│   ├── 04_hold_branch/
│   └── 05_records/
├── postprocess/
│   ├── peak_criterion/
│   ├── section_load/
│   ├── bond_tracking/
│   ├── fibre_force/
│   └── debond_intervals/
└── data/
    ├── raw/
    ├── initial/
    ├── lab/
    ├── figures/
    └── tables/
```

## Software environment

- **Numerical model:** PFC3D 6.0 with embedded Python 3.6.
- **Offline analysis:** Python 3.12, NumPy and pandas.

The post-processing scripts operate on exported CSV data and do not require PFC. Detailed dependencies and execution instructions accompany the code release.

## Data conventions

CSV files use UTF-8 encoding. Files ending in `.csv.gz` are compressed CSVs.

- Processed coordinates labelled `_mm` are in millimetres.
- Forces labelled `_N` are in newtons.
- `strain_pct = 1.25` denotes 1.25% axial strain.
- Raw PFC coordinates use metres, and raw strain is dimensionless.
- Fibre axial force is positive in tension.
- Sectional net load is positive in compression.
- Paired comparisons are identified as **test / reference**.
- Recorded quality warnings are retained.

Actual saved states, loading endpoints and comparison definitions are documented with the data.

## Scope

The shared data and scripts support inspection of the modelling procedures and recalculation of the supplied post-processing results. PFC saved states and a complete simulation restart environment are not included.

Model-source coverage and unavailable data are documented in `COMPLETENESS.md`. Experimental data retain their original source citations.

## License

- **Code:** MIT License.
- **Contributed data and documentation:** Creative Commons Attribution 4.0 International, subject to the source notices supplied with the release.

See `LICENSE` for details. Source publications and third-party materials retain their original terms.

When reusing this resource, please acknowledge the repository, identify the version used and retain the experimental-data citations.

## Contact

Questions, corrections and suggestions are welcome through GitHub Issues.

**Shangjun Zhao**  
Email: [zhaoshangjun@foxmail.com](mailto:zhaoshangjun@foxmail.com)
