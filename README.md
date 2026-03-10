# 🕵️‍♂️ DSP & Image Steganography: The "Nothing to See Here" Project

> *A robust MATLAB implementation of LSB steganography and cryptography. Built by a 4th-year B.Tech ECE student trying to hide data from everyone (mostly from my examiners).*

![MATLAB](https://img.shields.io/badge/Language-MATLAB-orange.svg?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-XOR_%2B_PRNG-brightgreen.svg?style=for-the-badge)
![Panic](https://img.shields.io/badge/Powered_by-4th_Year_Panic-red.svg?style=for-the-badge)
![Bugs](https://img.shields.io/badge/Bugs-Features_in_Disguise-blue.svg?style=for-the-badge)

---

## 📜 Executive Summary (What is this?)
This repository contains a fully functional Digital Signal Processing (DSP) toolkit for **Secure Image Steganography**. It takes highly classified text, encrypts it, and buries it deep inside the Least Significant Bits (LSB) of a cover image's matrix. 

To the human eye? It's just a normal picture. To the MATLAB compiler? It's a top-secret data payload. To me? It's my academic portfolio.

---

## ✨ Core Features (Why it's cool)
* **Standard LSB Embedding:** Sequentially alters the very last bit of the image's pixel matrix. It is simple, effective, and completely invisible to human perception.
* **PRNG-Based Random Scattering:** Why hide things in a predictable straight line? Using `randperm` and a secret user-defined seed, this feature scatters your message bits across the image like confetti. Good luck extracting that without the seed!
* **XOR Cryptographic Cipher:** Adds a layer of bitwise XOR encryption before embedding. Even if someone manages to extract the scattered bits, it looks like absolute gibberish without the matching key.
* **Modular Design:** Built with future security upgrades in mind.

---

## 📂 The Vault (File Structure)
```text
DSP/
├── aes_final.m             # The VIP Lounge (Architecture placeholder for upcoming AES)
├── message.txt             # Your secret diary goes here (Test payload file)
├── stegancoder.m           # Standard sequential encoder (The reliable workhorse)
├── stegancoder_Rand.m      # The chaotic encoder (Scatters data unpredictably)
├── stegandecoder.m         # Standard sequential decoder (Brings your data back)
└── stegandecoder_Rand.m    # The chaotic decoder (Needs the exact seed to work)
```

---

## 🛠️ Prerequisites
1. **MATLAB** (Tested on recent versions. If it crashes on yours, let's just blame the version).
2. An image to use as a cover (`.png` or `.bmp` format is highly recommended to avoid losing your hidden bits to JPEG compression).
3. A basic understanding of matrices (or at least the ability to pretend you understand them during presentations).

---

## 🚀 How to Execute (Without breaking anything)

### Method A: The "Keep It Simple" Approach (Sequential)
```matlab
% 1. Load an unsuspecting image
cover_image = imread('innocent_cat.png');

% 2. Encode with a secret cryptographic key (e.g., 123)
% Warning: Do not use 'password' as your secret message. Be creative.
stego_img = stegancoder(cover_image, 'My DSP project actually compiles!', 123);

% 3. Save it before you lose it
imwrite(stego_img, 'secret_cat.png');
```

### Method B: The "Tin Foil Hat" Approach (Random Scattering)
```matlab
% Hide the data with a key (123) AND a secret seed (42) for maximum paranoia
stego_img = stegancoder_Rand(cover_image, 'They will never find this.', 123, 42);

% To read it back, you MUST remember both the key and the seed!
hidden_msg = stegandecoder_Rand(stego_img, 123, 42);
disp(hidden_msg);
```

---

## 🔮 Future Scope (To-Do List before graduation)
- [ ] **Activate the `aes_final.m` script:** Upgrade the basic XOR cipher to a full, government-grade Advanced Encryption Standard (AES) implementation.
- [ ] **Image Quality Metrics:** Add a script to calculate PSNR (Peak Signal-to-Noise Ratio) and MSE (Mean Squared Error) to mathematically prove the image isn't ruined.
- [ ] **Capacity Checking:** Make the code automatically scream at you if you try to hide an entire novel inside a tiny 50x50 pixel image.

---
<div align="center">
  <i>Architected, coded, and debugged by <b>Pallela Sai Manoj Kumar</b>.</i><br>
  <i>B.Tech Electronics & Communication Engineering</i>
</div>
