# Sichuan–Yunnan GNSS velocity-field results

Supplementary results for *Partition Stability and Local Relative Motion from GNSS Velocities in Sichuan and Yunnan*. Section, figure and table numbers refer to the revised manuscript and its online supplement.

## Common-motion results and checks

Main text Sections 2.6 and 3.2–3.3. Supplement Appendix S1 and Tables S1–S5.

| File | Contents |
| --- | --- |
| [station_residual_velocities.csv](common_motion/station_residual_velocities.csv) | Station-level east and north residual velocities after removing the GLS translation, arithmetic mean or GLS Euler rotation (mm/yr). |
| [paired_repetitions.csv](common_motion/paired_repetitions.csv) | Trial-level K, silhouette scores and adjusted Rand indices for the original field and two common-motion removals. |
| [boundary_matches.csv](common_motion/boundary_matches.csv) | Geometric matching for the reference boundaries by common-motion comparison and distance tolerance. |
| [implementation_checks.json](common_motion/implementation_checks.json) | Numerical discrepancies from the EV, PT and Euler design-matrix checks. |
| [reference_reproduction.json](common_motion/reference_reproduction.json) | Numerical checks against archived reference windows and distances. |

## Unit-basis candidate boundaries and fixed-window results

Main text Sections 3.3–3.4, Tables 3–4 and Figs. 2–4. Supplement Appendix S4, Fig. S5, Table S14 and Fig. S6.

| File | Contents |
| --- | --- |
| [candidate_line_vertices.csv](unit_basis_windows/candidate_line_vertices.csv) | Ordered vertices for each smoothed line in the local east–north plane (km), identified by label_case and boundary_id. |
| [window_centers_and_normals.csv](unit_basis_windows/window_centers_and_normals.csv) | Window centers, positive normals and selected station indices for the re-extracted profiles. |
| [geometry_metadata.json](unit_basis_windows/geometry_metadata.json) | Projection origin, geometry settings and case labels. |
| [profile_station_projections.csv](unit_basis_windows/profile_station_projections.csv) | Original stations with normal distance, normal velocity and its standard deviation. |
| [additional_station_projections.csv](unit_basis_windows/additional_station_projections.csv) | Corresponding values for additional stations in the unit-basis Boundary 3 window. |
| [profile_side_mean_tests.csv](unit_basis_windows/profile_side_mean_tests.csv) | Two-side mean velocity contrasts and tests by profile and error scenario. |
| [additional_station_side_mean_tests.csv](unit_basis_windows/additional_station_side_mean_tests.csv) | Fixed-window contrasts and conditional tests for additional stations. |
| [profile_models.csv](unit_basis_windows/profile_models.csv) | Original-station model fits, AICc, central jumps and transition widths by error scenario. |
| [additional_station_models.csv](unit_basis_windows/additional_station_models.csv) | Corresponding model fits for additional stations in the main window. |
| [boundary_recurrence_trials.csv](unit_basis_windows/boundary_recurrence_trials.csv) | Trial-level boundary matches after spatial subsampling and velocity perturbation. |
| [window_to_fault_distances.csv](unit_basis_windows/window_to_fault_distances.csv) | Center-to-fault and window-to-fault distances, fault map sources and intersection flags for the three valid windows. |
| [station_pair_counts.npz](unit_basis_windows/station_pair_counts.npz) | Co-sampling and same-cluster count matrices underlying Fig. S5. Divide corresponding counts where the co-sampling count is positive. |
| [station_pair_index.csv](unit_basis_windows/station_pair_index.csv) | Station order and full-sample clusters for the rows and columns in station_pair_counts.npz. |

## Shifted-window results

Main text Sections 2.7 and 3.5, especially the note to Table 5 and Fig. 5.

| File | Contents |
| --- | --- |
| [scenario_results.csv](shifted_windows/scenario_results.csv) | Contrasts, intervals and model comparison summaries for the seven error scenarios, with coverage flags. |
| [model_comparison.csv](shifted_windows/model_comparison.csv) | AICc, slopes and residual dispersion for individual models at each shift and error scenario. |
| [station_records.csv](shifted_windows/station_records.csv) | Station membership, local coordinates, projected velocities and coverage flags at each shift. |
| [window_geometry.csv](shifted_windows/window_geometry.csv) | Centers, normals, station counts, center gaps and overlap with the main window. |
| [window_overlap.csv](shifted_windows/window_overlap.csv) | Pairwise station overlap counts and Jaccard indices across shifts. |

## Additional-station provenance and deduplication

Main text Sections 2.5 and 4.4. Supplement Appendix S6.1 and Table S17. The source velocity archive is [Zenodo record 15553578](https://zenodo.org/records/15553578).

| File | Contents |
| --- | --- |
| [fixed_window_station_provenance.csv](station_provenance/fixed_window_station_provenance.csv) | Source lines and nearest original stations for the 22 distinct additional stations in the two fixed windows. The in_unit_16 flag identifies Table S17 stations. |
| [shifted_window_station_provenance.csv](station_provenance/shifted_window_station_provenance.csv) | Source lines, nearest-station distances and shifted-window membership for the additional stations. |
| [shared_station_velocity_differences.csv](station_provenance/shared_station_velocity_differences.csv) | Matched station IDs and calculated velocity differences for all 473 shared stations (mm/yr). |
| [shared_station_diagnostic_summary.csv](station_provenance/shared_station_diagnostic_summary.csv) | Summary for all 473 matched stations and the 456 within the study area. |

## Paired synthetic trials

Main text Sections 2.8 and 3.6, Table 6 and Fig. 6. Supplement Appendix S6.2 and Table S18.

| File | Contents |
| --- | --- |
| [protocol.json](synthetic_benchmark/protocol.json) | Station geometry, velocity profiles, noise and matching criteria specified for the synthetic trials. |
| [station_geometry.csv](synthetic_benchmark/station_geometry.csv) | Station order, coordinates, normal distance x (km) and reference side for the 455 sites. |
| [paired_noise.npz](synthetic_benchmark/paired_noise.npz) | Standard-normal draws and derived east and north noise (mm/yr). The 100 × 455 × 2 array axes are trial, station and component. |
| [realization_results.csv](synthetic_benchmark/realization_results.csv) | 1,200 results for the paired noisy trials. Includes K, silhouette, ARI and geometric matching measures. |
| [noiseless_results.csv](synthetic_benchmark/noiseless_results.csv) | 12 results for the noiseless comparison, identified by repetition 0. |
| [paired_match_summary.csv](synthetic_benchmark/paired_match_summary.csv) | 20 km paired match counts, median ARIs and exact McNemar p values for Table S18. |
| [validation.json](synthetic_benchmark/validation.json) | Checks of row counts, pairing, noise regeneration and noiseless step fields. |
| [candidate_line_vertices.npz](synthetic_benchmark/candidate_line_vertices.npz) | Full smoothed candidate lines before clipping, recovered from the archived trial configuration. See Data formats below. |

## Data formats

CSV and JSON files are UTF-8. NPZ files contain NumPy arrays and can be opened with allow_pickle=False. Station identifiers refer to public GNSS monitoring stations.

In candidate_line_vertices.npz, each row of line_index contains the zero-based trial index, one-based line number within the trial, and the zero-based start and exclusive end indices into vertices_xy_km. The background, amplitude_mm_yr, repetition and method arrays identify the same trials as the two results CSV files. Coordinates are east and north in kilometres in the study local projection. The longitude and latitude of the origin are stored as origin_lon_lat. The coordinate export reproduced the archived trial results and noise arrays.
