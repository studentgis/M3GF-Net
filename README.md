# M3GF-Net: A Multimodal Multi-task Framework for Integrating Geological Semantics and Structural Attributes in Borehole Data Interpretation

![Python 3.10](https://img.shields.io/badge/Python-3.10-blue.svg)
![PyTorch 2.7.1](https://img.shields.io/badge/PyTorch-2.7.1-EE4C2C.svg)

Official implementation of the paper:

**"M3GF-Net: A Multimodal Multi-task Framework for Integrating Geological Semantics and Structural Attributes in Borehole Data Interpretation"**

---

## 📖 Overview

M3GF-Net is a physics-informed multimodal multi-task learning model designed for subsurface geological interpretation.

By synergistically utilizing numerical geological structural attributes (e.g., layer depth and layer thickness) and textual geological descriptions, the model performs **joint prediction for lithology classification and stratigraphic unit division**.

### Key Components

- **RoBERTa + BiLSTM** Extract deep semantic representations from geological description texts.

- **Fully Connected Networks (FCNs)** Project numerical structural attributes (depth and thickness) into a high-dimensional feature space.

- **Gated Multimodal Unit (GMU)** Dynamically fuse textual and numerical modalities.

---

## ⚙️ Setup & Installation

### Requirements

- Python 3.10
- CUDA-enabled GPU (recommended)

### 1. Clone repository

```bash
git clone https://github.com/studentgis/M3GF-Net.git
cd M3GF-Net
```

### 2. Create environment

```bash
conda create -n m3gf_env python=3.10
conda activate m3gf_env
```

### 3. Install dependencies

```bash
pip install torch==2.7.1 torchvision==0.22.1 torchaudio==2.7.1 --index-url [https://download.pytorch.org/whl/cu118](https://download.pytorch.org/whl/cu118)

pip install transformers==4.52.4 scikit-learn pandas numpy jupyter
```

---

## 🗂️ Data

For demonstration purposes, this repository includes a **simulated dataset** (`train.csv`, `val.csv`, `test.csv`) to help you run and verify the model pipeline immediately. 

To train the model on your own dataset, please format your CSV files with the following essential columns:

- `text`: Textual geological description.
- `depth`: Normalized depth.
- `thickness`: Normalized thickness.
- `lithology_label`: Class ID for lithology (0-6).
- `lithostratigraphic_unit_label`: Class ID for stratigraphic unit (0-7).

---

## 🚀 Quick Start

1. Launch Jupyter Notebook:

```bash
jupyter notebook
```

2. Open:

```text
M3GF-Net.ipynb
```

3. Run the notebook:

```text
Kernel → Restart & Run All
```

The pipeline will perform:

* Dataset loading and batch processing
* Text tokenization and numeric feature extraction
* Feature encoding and multimodal fusion (via GMU)
* Joint multi-task model training
* Model evaluation and classification report generation

Outputs will be saved in:

```text
result_base/
```

Including:

* `best_model.pth`
* `results_best.txt`
* `training_history.csv`
* `results_epochfinal.txt`

---

## 📂 Project Structure

```text
M3GF-Net/
│
├── M3GF-Net.ipynb      # Main training pipeline
├── train.csv           # Simulated training dataset
├── val.csv             # Simulated validation dataset
├── test.csv            # Simulated testing dataset
├── result_base/        # Output directory (generated automatically)
└── README.md
```

---


## 📧 Contact

For questions or collaborations:

Gang Liu
Email: [liugang2014@cdut.edu.cn](mailto:liugang2014@cdut.edu.cn)

---

## 📄 License

This project is released under the **MIT License**.
If you use this code in your research, please cite our work.
