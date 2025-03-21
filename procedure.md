# 🧪 Methodology: Underwater Image Enhancement using DIRS-CLAHS

This document outlines the step-by-step methodology used to enhance underwater images using the DIRS-CLAHS method, applied on the UIEB dataset (Challenging-60 subset).

---

## 1. Dataset
- **UIEB (Underwater Image Enhancement Benchmark)**  
- Used the **Challenging-60** subset containing severe green cast and color distortion.
- Real-world underwater images without ground truth references.

---

## 2. Pre-processing
### 🔴 Red Channel Boost
- Applied before enhancement to recover lost red color components.
- Addresses color imbalance due to higher absorption of red light in water.

---

## 3. DIRS-CLAHS Enhancement Pipeline
### A. Global Contrast Correction
- Computed histogram parameters: min, max, and midpoints.
- Dual-intensity image composition using upper and lower histogram stretches.

### B. Local Contrast Enhancement (CLAHS)
- Image divided into 2x2 tiles.
- CLAHS applied with clip limit to avoid over-enhancement.
- Remapping of histograms using Rayleigh distribution.
- Final image reconstructed via bilinear interpolation.

### C. Color Correction in HSV
- Image converted from RGB to HSV.
- S (saturation) and V (value) channels enhanced via histogram stretching.
- Merged lower and upper stretched values for smooth enhancement.
- Converted back to RGB.

---

## 4. Post-processing
### 🎨 LAB Color Space Cast Removal
- Converted enhanced image to LAB space.
- Removed residual green/blue cast for color naturalness.
- Improved perceptual quality and color fidelity.

---

## 5. Summary
This multi-step pipeline combines both contrast and color correction in a physically informed and perceptually optimized manner, designed for robust enhancement across diverse underwater conditions.
