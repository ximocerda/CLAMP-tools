# CLAMP-tools

Companion software tools for the **CLAMP dataset**: exploration, visualization, and export utilities for multimodal hand posture and grasp-phase analysis.

Dataset DOI:
https://doi.org/10.5281/zenodo.20555985

## Overview

This repository provides a Jupyter Notebook for loading, exploring, visualizing, and exporting selected groups from the CLAMP dataset.

CLAMP (**CLassified and Annotated Multimodal Postures**) is a multimodal dataset containing surface electromyography (sEMG), accelerometer, and gyroscope recordings acquired during predefined hand postures and grasp-related tasks.

## Contents

```text
CLAMP_dataset_explorer.ipynb
requirements.txt
LICENSE
README.md
```

## Dataset

The CLAMP dataset is available through Zenodo:

https://doi.org/10.5281/zenodo.20555985

The dataset is distributed separately from this software repository. It includes two main folders:

```text
raw_data/
processed_data/
```

The notebook mainly uses the `processed_data/` folder. The `raw_data/` folder contains the original MATLAB recordings.

## Installation

Clone or download this repository and install the required Python dependencies:

```bash
pip install -r requirements.txt
```

The required packages are:

```text
numpy
pandas
matplotlib
ipywidgets
jupyterlab
```

## How to use the notebook

1. Download the dataset ZIP files from Zenodo.
2. Download or clone this GitHub repository.
3. Place the dataset ZIP files in the same directory as `CLAMP_dataset_explorer.ipynb`.
4. Run the notebook.

Before extraction, the folder may look like this:

```text
CLAMP_dataset_explorer.ipynb
raw_data.zip
processed_data.zip
```

After extraction, the expected structure is:

```text
CLAMP_dataset_explorer.ipynb
raw_data/
processed_data/
```

The notebook checks whether the dataset folders are available and extracts the ZIP files if needed.

## Notebook functionality

The notebook allows users to:

* select the signal modality: `emg`, `acc`, or `gyro`;
* access data grouped by posture or by subject and posture;
* visualize signal segments;
* inspect trial-level and sample-level annotations;
* optionally display only samples belonging to the grasp interval;
* export selected complete dataset groups to a local `exports/` folder.

The export tool copies the complete selected group from `processed_data/`. It does not generate a filtered or modified dataset, in order to preserve the relationship between signal matrices, annotations, trial descriptors, and metadata.

## Dataset structure

The processed dataset is organized by modality:

```text
processed_data/
├── emg/
├── acc/
└── gyro/
```

Each modality includes two grouping strategies:

```text
by_subject_posture/
by_posture/
```

Each processed group contains:

```text
matrix.npy
bundle.mat
trials.csv
index.csv
metadata.json
```

## Authors

* Marta C. Mora
* Noora Hamzah Shadahan Al-Owaidi
* Bàrbara Pellicer-Coves
* Jose V. García-Ortiz
* Joaquín Cerdá-Boluda

## Citation

If you use this dataset or the accompanying software tools, please cite the CLAMP dataset and the associated article.

Dataset DOI:
https://doi.org/10.5281/zenodo.20555985

## License

The software tools in this repository are distributed under the MIT License.

The CLAMP dataset itself is distributed separately through Zenodo under the Creative Commons Attribution 4.0 International License (CC BY 4.0).
