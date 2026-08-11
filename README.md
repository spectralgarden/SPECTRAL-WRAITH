```==============================================================================
                           SPECTRAL GARDEN — SPECTRAL WRAITH
==============================================================================

Spectral Bin-Freezing • Phase Smearing • Density Gating • FFT Manipulation
Windows 64‑bit VST3 • Built with JUCE • Frequency-Domain Audio Engine

==============================================================================

Spectral Wraith is a frequency-domain audio processor that captures spectral
snapshots, dissolves them into drifting phase clouds, and reshapes sound into
evolving drones, metallic resonances, and ethereal spectral textures. It
decouples magnitude and phase information inside a 2048‑point FFT engine,
allowing freeze, smear, drift, and probabilistic bin gating.

This document provides a complete user guide and developer manual.

==============================================================================

1. USER GUIDE
==============================================================================

1.1 Concept

Spectral Wraith transforms incoming audio into frequency bins using a 2048‑point
FFT. Magnitude and phase are manipulated independently, enabling:

• Spectral freezing
• Gaussian blur smearing
• Bin-width grouping
• Phase drift modulation
• Density-based bin gating

The result is a spectral “ghost” that drifts through phase space.

------------------------------------------------------------------------------

1.2 Interface Layout

Left Panel — Manifestation Controls  
    Six rotary knobs controlling freeze, smear, bin width, drift, density, and mix.

Center Panel — Spectrogram  
    Vertical waterfall display with dynamic color interpolation.

Right Panel — Ritual Presets  
    Smooth-scrolling preset browser with Save Ritual button.

------------------------------------------------------------------------------

1.3 Control Parameters

FREEZE  
    Blends real-time input with a frozen spectral snapshot.

SMEAR  
    Gaussian blur applied to spectral magnitudes.

BIN WIDTH  
    Groups adjacent frequency bins (1 → 32) for coarse resolution.

PHASE DRIFT  
    Frequency-weighted LFO modulation of bin phases.

DENSITY  
    Probability gate for bin survival (0 → sparse, 1 → full spectrum).

DRY/WET  
    Linear crossfade between dry input and processed output.

------------------------------------------------------------------------------

1.4 Preset Management

Selecting Presets  
    Scroll the Ritual Presets list and click to load.

Saving Presets  
    • Adjust controls  
    • Click SAVE RITUAL  
    • Enter name  
    • Preset saved as XML and added to the list

==============================================================================

2. TECHNICAL & DEVELOPER MANUAL
==============================================================================

2.1 DSP Signal Flow

Stereo streams processed independently:

