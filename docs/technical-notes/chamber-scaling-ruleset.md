# Tech Notes(02) — Chamber Scaling Ruleset (Draft v0.1)

<span style="color:#1e40af; font-weight:bold;">
“This ruleset was developed to standardize the format. The coefficient (k) should ideally be determined based on actual operating data.”
</span>

## A. Geometry & Reference Ratios

1. Define chamber inner diameter **D** and hot-zone length L (refractory hot zone).
2. Maintain **hot-zone slenderness** within: **L/D = 3.0–4.5** for stable staged gas-phase oxidation.

## B. Central Rod (Mixing Spine)

3. Set central rod diameter as a fixed fraction of D:
 &nbsp;d_rod = k_r · D, where k_r = 0.06–0.12 (select one k_r and keep constant across sizes).

4. Keep rod tip / leading edge located inside the primary reaction zone:
   x_tip ≈ 0.15–0.25 · L from the feed-side reference plane (constant fraction).

## C. Air Nozzle Staging (Temporal Split of Oxidation)

5. Select number of air stages **N_stage** by L/D:

L/D < 3.0 → N_stage = 2–3

3.0 ≤ L/D ≤ 4.0 → N_stage = 3–4

L/D > 4.0 → N_stage = 4–6

Place stages at normalized axial positions (from feed-side):
x_i / L = {0.15, 0.35, 0.55, 0.75, 0.90} (use first N_stage points).

D. Nozzle Count & Symmetry (Flow Architecture)

Use symmetric nozzle counts per stage to form stable swirl / cross-mixing:
n_i ∈ {6, 8, 12} (avoid odd counts unless field-proven).

Start rule:

Primary stage: n₁ = 6–8 (anchor + ignition)

Middle stages: n_mid = 6–8 (mixing + cracking)

Final stage: n_last = 6–12 (polishing oxidation)

E. Air Pressure Control (Velocity-Based Standard)

Standardize by nozzle exit velocity, not gauge pressure:
Target V_exit bands (choose one per stage and keep constant across scale):

Primary: V₁ = 25–45 m/s

Middle: V_mid = 20–40 m/s

Final: V_last = 15–35 m/s

Convert V_exit to operating pressure using nozzle area & supply line losses:
P_set(stage) = f(V_exit, A_nozzle_total, ΔP_line, temperature)
→ Document P_set as a table per chamber size after commissioning.

F. Commissioning Acceptance Criteria (Smoke-Free Stability)

Acceptance is defined by: stable low-luminosity flame + no visible smoke + no persistent odor under worst-case SPCW feed.

If instability appears: adjust in this order only:
(i) stage airflow split → (ii) V_exit (pressure) → (iii) nozzle count/layout → (iv) k_r (rod ratio)
