# CS4190 Final Project

Deep learning class project using PyTorch, OpenCV, and Streamlit.

## Tech Stack

- **Python 3.13**
- **PyTorch / torchvision**: model building and training
- **OpenCV**: image processing
- **NumPy**: numerical computing
- **Jupyter**: experiments and exploration
- **Streamlit**: web app demo

## Project Structure

```
CS4190FinalProject/
├── app.py              # Streamlit web app
├── notebooks/          # Jupyter notebooks for experiments
├── src/                # Reusable Python code (models, data loading, utils)
├── data/               # Datasets (not tracked by git)
├── models/             # Saved model weights (not tracked by git)
├── requirements.txt    # Python dependencies
└── .vscode/            # VS Code settings and recommended extensions
```

## Setup

1. **Clone the repo**
   ```bash
   git clone <repo-url>
   cd CS4190FinalProject
   ```

2. **Create and activate a virtual environment**
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate        # macOS / Linux
   .venv\Scripts\activate           # Windows
   ```

3. **Install dependencies**
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

4. **Register the Jupyter kernel** (optional, makes the venv selectable in notebooks)
   ```bash
   python -m ipykernel install --user --name cs4190 --display-name "Python (CS4190)"
   ```

5. **VS Code**: install the recommended extensions when prompted (Python and Jupyter).

## Usage

### Run the Streamlit app
```bash
streamlit run app.py
```
Then open http://localhost:8501 in your browser.

### Use Jupyter notebooks
Create or open a `.ipynb` file in `notebooks/` and select the **Python (CS4190)** or `.venv` kernel in the top-right corner of VS Code.

Or launch Jupyter in the browser:
```bash
jupyter notebook
```

## GPU Support

PyTorch picks the best available device:

```python
import torch

if torch.cuda.is_available():
    device = "cuda"      # NVIDIA GPU
elif torch.backends.mps.is_available():
    device = "mps"       # Apple Silicon GPU
else:
    device = "cpu"
```

On Apple Silicon, if an operation is not supported on MPS, set this to fall back to the CPU:
```bash
export PYTORCH_ENABLE_MPS_FALLBACK=1
```

For NVIDIA GPUs on Windows/Linux, install the CUDA build of PyTorch from https://pytorch.org/get-started/locally/.

## Data

Put datasets in the `data/` folder. It is git-ignored, so large files are not committed. Explain here how teammates can download the dataset:

> _TODO: add dataset source and download instructions._

## Team

> _TODO: add team members._
