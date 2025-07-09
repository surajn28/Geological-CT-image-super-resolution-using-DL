# DR-SCAN: Dual-Branch Deep Residual Network for Human-in-the-Loop Super-Resolution

DR-SCAN is a deep learning framework for single-image super-resolution that combines a dual-branch residual architecture (shallow & deep) with channel and spatial attention (CBAM-style). The project features an interactive Streamlit UI for human-in-the-loop (HITL) branch fusion and real-time perceptual tuning.

## Features
Dual-Branch Architecture: Separate shallow and deep residual branches for global structure and local detail, with CBAM (channel and spatial attention) in every block.

Supports Multiple Scaling Factors: Training and inference scripts for 2x, 3x, and 4x super-resolution.

Human-in-the-Loop UI: Streamlit-based interface for interactively tuning branch weights and optimizing for perceptual quality (LPIPS).

Datasets: Trained on DIV2K and Flickr2K; evaluation on Set5, Set14, BSD100.

## Steps to run:

- Clone the repository
  -  git clone https://github.com/surajn28/DR-SCAN.git
  -  cd DR-SCAN
- Install dependencies
  -  pip install torch torchvision pillow numpy streamlit lpips pytorch-msssim
- Training:
  - python drscan_2x.py (change the script name likewise to tran models of different resolution)
- Interactive UI:
  - streamlit run drscan_ui.py
  - Upload a model checkpoint (.pth) trained for your desired scale factor.
  - Upload a low-resolution (LR) input image.
  - (Optional) Upload a high-resolution (HR) ground truth image to enable LPIPS-based perceptual search.
  - Adjust shallow/deep branch weights manually or use the "Local Search" to find optimal weights for best perceptual quality.
