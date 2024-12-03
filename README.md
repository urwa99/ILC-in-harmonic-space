# ILC-in-harmonic-space
Internal Linear Combination of simulated CMB maps and foregrounds in harmonic space
Performing ILC in harmonic space (as opposed to pixel space) allows for better control over spatial scales using spherical harmonic decomposition.

- **Transform Frequency Maps to Harmonic Space**:

Each map $M_i(\hat{n})$ (where $i$ represents a frequency channel and $\hat{n}$ represents a sky direction) is decomposed into spherical harmonics:

$$
M_i(\hat{n}) = \sum_{l,m} a^i_{lm}Y_{lm}(\hat{n})
$$

where $a^i_{lm}$ are the harmonic coefficients

- Compute Covariance Matrix

covariance matrix of the harmonic coefficients:

``` math
C^{ij}_l = \langle a^i_{lm} a^{j*}_{lm} \rangle
```

where $i$, $j$ are the frequency channels

- Compute weights that minimize variance of the combined map while preserving the CMB signal:

```math
\omega_i(l) = \frac{\sum_j (C_l^{-1})_{ij} b_{j}}{\sum_{ij}b_i (C_l^{-1})_{ij} b_{j}}
```

where $b_i$  represents the CMB transfer function. $b_i = [1,...,1]$

- Combine maps

Construct the harmonic coefficients of the cleaned map.

```math 
a^{ILC}_{lm} = \sum_i w_i(l)a^i_{lm}
 ```

- Reconstruct the map
- Compute the power spectrum
