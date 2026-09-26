# Nighttime De-Fogging Vision Network with Smart Glare Suppression

Laptop-friendly prototype matching the project proposal: OpenCV/image preprocessing, CNN local feature extraction, Transformer-style global context, attention, feature fusion, nighttime enhancement, and PSNR/SSIM evaluation.

## Run locally

```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

pip install -r requirements.txt
python train.py --epochs 3
streamlit run app.py
```

The bundled prototype is designed for CPU-only laptops. A GPU can be used automatically by PyTorch when available.

## Dataset

For an academic experiment, use the official NT-HAZE 2026 paired nighttime dehazing dataset. Dataset instructions are in DATASET.md. Third-party dataset files should not be committed to this repository.

The bundled checkpoint is trained on small synthetic nighttime degradation pairs so the demo is immediately runnable; it is not presented as a real-dataset benchmark result.

## Architecture

Input -> CNN local features -> attention -> Transformer global context -> feature fusion -> enhanced image.
