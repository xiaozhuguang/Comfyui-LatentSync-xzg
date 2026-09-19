# Comfyui-LatentSync-XZG

ComfyUI custom node for **LatentSync 1.6** lip sync (ByteDance).

## Based on

Derived from [ComfyUI-LatentSyncWrapper](https://github.com/ShmuelRonen/ComfyUI-LatentSyncWrapper), which vendors the official ByteDance LatentSync source.

## What this fork fixes

- **Green mouth / decode artifacts** — VAE is locked to fp32 + sliced decoding, fixing the green-block mouth issue on 1.6.
- **VRAM OOM / system lockup** — hard-capped per-process VRAM fraction, batch size = 1, UNet pinned to GPU, eliminating the 48 GB spike that froze Windows.

## Install

```
cd ComfyUI/custom_nodes
git clone https://github.com/xiaozhuguang/Comfyui-LatentSync-XZG.git
```

Download models to `ComfyUI/models/checkpoints/LatentSync-1.6/`:
- `latentsync_unet.pt`
- `whisper/tiny.pt`
- `vae/` (sd-vae-ft-mse)
- `models/buffalo_l/` (insightface face detector)

Then restart ComfyUI.
