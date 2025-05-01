# Taktpixel2025PD-CD: Taktpixel 2025 Printing Defect Change Detection Dataset

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)

## Overview

**Taktpixel2025PD-CD** is a benchmark dataset designed for evaluating image change detection models in the context of printed material inspection. It consists of image pairs representing master (reference) and target (possibly defective) scans of printed samples, along with pixel-wise binary maps indicating defect regions.

The dataset simulates practical defect scenarios observed in industrial printing processes (e.g., offset and inkjet), and includes a wide variety of real-world defects such as black spots, misregistrations, and surface contaminants.

## Download

The dataset can be downloaded from [Zenodo](https://doi.org/10.5281/zenodo.15318802).

## Directory Structure

The dataset is organized into three subsets: `train`, `val`, and `test`. Each subset contains the following three directories:

- `A/` — master images (reference, defect-free)
- `B/` — target images (with defects)
- `OUT/` — binary masks indicating defect regions (1: defect, 0: background)

```
Taktpixel2025PD-CD/
├── train/
│   ├── A/     # master images
│   ├── B/     # target images
│   └── OUT/   # defect masks
├── val/
│   ├── A/
│   ├── B/
│   └── OUT/
├── test/
│   ├── A/
│   ├── B/
│   └── OUT/
├── README.txt
├── legalcode.txt
```

File names follow a pattern that includes the defect category for easier filtering and analysis (e.g., `blackspot_proofrog_a4pera_back_00003_0012.png`).

## Defect Categories

The dataset includes the following six defect types:

| Category     | Description                                                                 | Train | Val | Test | Total |
|--------------|-----------------------------------------------------------------------------|-------|-----|------|-------|
| Black spot   | Black stains or ink blobs on the printed surface                            | 1,262 | 158 | 158  | 1,578 |
| Color shift  | Color misregistration due to misaligned printing plates                     | 1,380 | 163 | 169  | 1,712 |
| Friction     | Missing ink caused by abrasion or insufficient transfer                     | 318   | 39  | 41   | 398   |
| Hair         | Hair contamination adhered to the ink or surface                            | 836   | 105 | 105  | 1,046 |
| Line         | Linear ink streaks aligned with print flow direction                        | 143   | 17  | 18   | 178   |
| Pinhole      | Small missing print spots due to debris on plates or paper                  | 328   | 41  | 42   | 411   |

Each category has been reviewed manually to ensure defect clarity and to exclude non-defect variations.

## Data Creation Process

Defect candidates were automatically extracted by comparing master and target scans using standard industrial inspection algorithms. Regions with significant differences were cropped with margins, and binary masks were manually refined to accurately represent defect regions. False positives due to natural printing variation were excluded through expert review.

## Use Cases

- Supervised training and benchmarking of change detection models
- Industrial visual inspection algorithm evaluation
- Academic research in defect detection and change localization

## License

This dataset is released under the [Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/) license.  
See [LICENSE](LICENSE) for the full license terms.

## Citation

If you use this dataset in your work, please cite it as follows:

```bibtex
@misc{tamaki2025taktpixel,
  author       = {Tamaki, Teppei},
  title        = {Taktpixel2025PD-CD: Taktpixel 2025 Printing Defect Change Detection Dataset},
  year         = {2025},
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.15318802},
  url          = {https://doi.org/10.5281/zenodo.15318802},
  note         = {Dataset}
}
```
