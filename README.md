# ML-Based-Automated-Earthquake-Detection-Association
Automated earthquake detection and association using machine learning (EQTransformer) and HYPOINVERSE

This repository contains a complete processing workflow using [EQTransformer](https://github.com/smousavi05/EQTransformer) to detect and associate local earthquakes from MiniSEED data.

## 🔍 Project Summary

This workflow was developed as part of the **BIMA project** (Bangladesh India Myanmar Array) to identify and relocate **local deep seismic events** that are **not listed in standard earthquake catalogs**. The method integrates:

- Preprocessing of raw MiniSEED waveform files
- Renaming and formatting input data for EQTransformer
- Detection of potential earthquakes
- Association of detected picks into events
- Generation of station metadata in EQTransformer-compatible format

The output **`Y2000.phs`** file from EQTransformer was further used as input to the **HYPOINVERSE** location program to relocate local deep earthquakes in **Myanmar**.

## 📓 Notebook

The main Jupyter notebook [`eqt_detection.ipynb`](./eqt_detection.ipynb) walks through all stages:

1. **MiniSEED preprocessing** – Rename and organize data
2. **Station metadata conversion** – Convert station list to EQTransformer format
3. **Earthquake detection** – Run EQTransformer on processed waveform data
4. **Phase association** – Group picks into events using EQTransformer’s associator
5. **Export picks** – Save associated phase data in `Y2000.phs` format for use in HYPOINVERSE

## 🗂 Directory Structure
├── BIMA_miniseed/               # Raw MiniSEED files
├── BIMA_miniseed_processed/     # Renamed waveform files for EQTransformer
├── json_bima/
│   └── station_list.json        # EQTransformer-compatible station metadata
├── association_bima/
│   └── Y2000.phs                # Output phase file for HYPOINVERSE
├── eqt_detection.ipynb          # Main analysis notebook
└── README.md

## 🧠 Use Case

This workflow is especially useful in:
- Microseismicity studies
- Catalog completion tasks
- Identifying uncataloged deep events in regional/local networks
- Generating input for traditional location tools like **HYPOINVERSE**

## 🛠 Dependencies

- Python 3.8+
- EQTransformer (with TensorFlow backend)
- ObsPy
- NumPy, Pandas, Matplotlib
- JupyterLab/Notebook

> ⚠️ EQTransformer requires a GPU and TensorFlow >= 2.5 for efficient processing.




