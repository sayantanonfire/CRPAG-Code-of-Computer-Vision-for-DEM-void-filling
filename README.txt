Digital Elevation Models (DEMs) often suffer from data voids due to steep slopes, snow cover, shadows, and sensor limitations, especially in high-relief mountainous regions like the Himalayas. These voids severely impact downstream applications such as hydrological modeling, landslide detection, and geomorphological analysis.

To address this, we developed the Conditional Residual Pyramid Attentional Generator (CRPAG) – a novel deep learning-based framework that intelligently fills DEM voids by combining elevation structure with spectral cues from Sentinel-2 imagery.


.

🔹 CRPAG Mechanism – Advanced DEM Void Filling

The Conditional Residual Pyramid Attentional Generator (CRPAG) is a specialized deep learning framework designed to reconstruct voids in Digital Elevation Models (DEMs) with high accuracy and terrain fidelity. Unlike conventional methods (e.g., interpolation, U-Nets, CNNs), CRPAG leverages multi-modal fusion, hierarchical attention, and hydrological priors to deliver state-of-the-art performance.

🧩 Step-wise Structure of CRPAG

Dual-Encoder Design

One encoder processes DEM features (structural topography).

Another encoder processes Sentinel-2 Red Band reflectance (spectral texture).

The two streams are harmonized to capture both terrain geometry and surface properties.

Improved Channel Attention Module (ICAM)

Performs cross-modal attention fusion between DEM and Sentinel-2 inputs.

Dynamically learns which channels (DEM slopes, spectral textures) are most informative in void regions.

Advantage: Ensures that snow/vegetation regions, which usually cause DEM voids, are reconstructed with greater accuracy.

Residual Pyramid Attention Blocks (RPAB)

Processes features at multiple spatial scales (50 m, 200 m, 500 m).

Captures local details (ridges, gullies) as well as regional patterns (basin-scale slopes, glacial valleys).

Residual skip connections preserve sharp gradients and prevent over-smoothing.

Integration of Auxiliary Hydrological Features

Stream networks and flow accumulation maps are injected as geophysical constraints.

Prevents creation of artificial depressions, stream discontinuities, or slope artifacts.

Advantage: Guarantees hydrological continuity, which traditional void-filling methods often fail to preserve.

Attention-Guided Reconstruction

Attention maps highlight areas with spectral ambiguity (snow cover, shadows).

The model selectively emphasizes either DEM geometry or spectral cues, depending on local terrain conditions.

This adaptability ensures robustness across varied landscapes.

🚀 Why CRPAG is State-of-the-Art Compared to Other Techniques

Vs. Interpolation (e.g., Kriging, IDW, Spline):

Traditional methods ignore multi-scale terrain cues and oversmooth elevation surfaces.

CRPAG, in contrast, learns structural and spectral dependencies directly from data.

Vs. Conventional CNN/U-Net Approaches:

U-Nets struggle in steep/high-relief terrains due to bottleneck compression and lack of hydrological priors.

CRPAG introduces pyramid attention + hydrological integration, preserving ridges and flow paths.

Vs. GAN-based Methods (e.g., PIT-CNET):

GANs often produce artifacts in void zones due to unstable adversarial training.

CRPAG’s residual + attention blocks reduce instability and yield smoother convergence with minimal artifacts.

Vs. Multi-Scale Curriculum Networks (e.g., MCU-Net-EDF):

MCU-Net-EDF performs reasonably in flat terrain but fails in high-slope regions (error spikes >100 m).

CRPAG consistently maintains low RMSE (<30 m) even in extreme relief zones.

🌟 Summary

The CRPAG mechanism is not just another deep neural network — it is a terrain-aware, multi-modal fusion framework that:

Integrates DEM + Sentinel-2 spectral data (multi-source).

Operates across multiple scales simultaneously.

Embeds hydrological priors for physically consistent void reconstruction.

Outperforms existing void filling models by 2–8× in accuracy while ensuring structural and hydrological fidelity.

📊 Performance & Validation

Accuracy Metrics:

RMSE: 9.1–28.9 m

MAE: 1.9–8.1 m

SSIM: 0.89–0.98 (structural fidelity preserved)

Moran’s I: 0.52–0.79 (spatial coherence retained)

Entropy-Based Evaluation:

Minimal Shannon Entropy & Configuration Entropy differences ensure both information content and spatial arrangement are preserved.

Comparative Superiority:

Outperformed state-of-the-art models like MCU-Net-EDF, HC-MAN, BSV-U-Net, and PIT-CNET in both statistical accuracy and terrain realism.

Showed resilience in large voids (>1 km²) and high-slope terrain (>30°).

🛰️ Why CRPAG is Different

Unlike traditional interpolation (kriging, spline, IDW), CRPAG avoids oversmoothing.

Unlike CNN/U-Net-only methods, CRPAG uses multi-modal fusion (DEM + spectral).

Unlike rule-based hydrological corrections, CRPAG dynamically adapts to terrain complexity.

In essence, CRPAG transforms void-filling from a patchwork correction into a data-driven reconstruction of true terrain surfaces.

🔧 Applications

Hydrological modeling (flow paths, flood simulations).

Landslide susceptibility and hazard mapping.

Glacier and snowpack monitoring.

Terrain continuity restoration in rugged mountainous DEMs.

📬 Contact

For algorithm-related issues or collaboration:
📧 Sayantan Mandal (Email) – sayantanonfire@gmail.com

🔗 LinkedIn – https://www.linkedin.com/in/sayantan-mandal-36a296213/
