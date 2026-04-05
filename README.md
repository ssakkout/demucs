
# Demucs-Torchcodec

**Demucs-Torchcodec** is a modernized fork of the [Original Demucs](https://github.com/facebookresearch/demucs).

While the original repository is no longer actively maintained, this fork continues the project by replacing the deprecated `torchaudio` decoding backends with the high-performance [**torchcodec**](https://github.com/pytorch/torchcodec) library.

### Why use this fork?

* **Modern Backend:** Uses `torchcodec` for faster and more robust audio decoding.
* **Dependency Lean:** Removes reliance on older `torchaudio` versions that often conflict with modern PyTorch installations.
* **Future Proof:** Designed to work with Python 3.10+ and the latest PyTorch ecosystems.

---

## Installation

### 1. Requirements

Before installing, ensure you have **FFmpeg** installed on your system (required by `torchcodec`):

* **Ubuntu/Debian:** `sudo apt-get install ffmpeg`
* **macOS:** `brew install ffmpeg`
* **Windows:** `choco install ffmpeg` (or download from [ffmpeg.org](https://ffmpeg.org))

### 2. Install the Package

```bash
pip install -U demucs-torchcodec
```

---

## Usage

The entry point for this version is `demucs-torchcodec`.

```bash
# Basic separation (defaults to htdemucs)
demucs-torchcodec test.mp3

# Separate into 2 stems (vocals and accompaniment)
demucs-torchcodec --two-stems=vocals test.mp3

# Use the high-quality fine-tuned model
demucs-torchcodec -n htdemucs_ft test.mp3
```

---

## Supported Models

This fork supports all standard Demucs v4 models, including:

* `htdemucs`: Hybrid Transformer Demucs (Default).
* `htdemucs_ft`: Fine-tuned version (Higher quality, slower).
* `hdemucs_mmi`: Hybrid Demucs v3 retrained.
* `mdx_extra`: Trained with extra data.

---

## Credits & License

**Original Author:** [Alexandre Défossez](https://github.com/adefossez).

This project is licensed under the  **MIT License** , exactly like the original Demucs. See the [LICENSE](LICENSE) file for details.

If you use this model in your research, please cite the original paper:

```bibtex
@inproceedings{rouard2022hybrid,
  title={Hybrid Transformers for Music Source Separation},
  author={Rouard, Simon and Massa, Francisco and D{\'e}fossez, Alexandre},
  booktitle={ICASSP 23},
  year={2023}
}
```
