# Literature survey for the open pieces D4, D5, D7, D8 (November 2026)

The pieces are those of `4Y-M/strong-coupling/forest/D_STATUS.md`:
- **D4**: mass off the chart on non-calm fibres;
- **D5**: fibre decay ⇒ constrained cube coefficient;
- **D7**: large fields are harmless;
- **D8**: multiscale composition and the crossover.

Each entry says what the work would mean for these four. "Checked" means I read the abstract or the listing; full texts
were not read unless said. Items marked *(unverified)* were seen only in search summaries.

## 1. Bałaban's renormalisation group and Dimock's re-exposition

- **The papers.**
  - Bałaban, CMP 1983–89: the series on lattice gauge theories, including the small- and large-field papers cited in
    `main.tex` as Bal84a and Bal89b.
  - J. Dimock, *The renormalization group according to Balaban*:
    - I, small fields, arXiv:1108.1335;
    - II, large fields, arXiv:1212.5562;
    - III, convergence, arXiv:1304.0705.

    It is worked out for φ⁴ in d = 3.
  - Dimock, *Covariant axial gauge*, arXiv:1410.2798. An abelian gauge compatible with block averaging. It addresses a
    problem Bałaban met when extending his method to pure Yang–Mills.
  - Dimock, QED on the 3-torus, math-ph/0210020, and *Ultraviolet regularity for QED in d = 3*, arXiv:1512.04373.
- **D8.** This is the reference framework. Bałaban controls the effective actions at every scale in finite volume at
  weak coupling (ultraviolet stability), but obtains no gap and no infinite-volume limit. Dimock II–III are the most
  readable account of how the small-field/large-field split is iterated. D8 has to reproduce this.
- **D7 and D4.** In Bałaban's scheme large-field regions are not shown to be rare in probability at each step. Each
  large-field cube carries a factor e^{−p(g_k)}, with p(g) → ∞ slowly as g → 0, which beats the combinatorics of the
  polymer expansion.
  - This is the per-site suppression that Conjecture L of `d5-calm/D5_CALM.md` needs. It holds under every exterior,
    because it comes from the action in one cube.
  - It is a better model for "local rarity under an arbitrary exterior" (ROADMAP §7 item 3) than the chessboard
    estimate, which needs the torus.
- **D5.** The small-field covariance bounds come from random-walk expansions of Green's functions with constraints,
  whose decay is exponential with scale-independent constants. This is the same mechanism as Theorem `chartdecay`
  together with the effective-locality theorems. Our explicit rate α_G = 2.5·10⁻⁴ is the analogue of Bałaban's
  unspecified constants.
- **The gauge.** Dimock's covariant axial gauge is the abelian precedent for the forest/block-tree gauge of
  Definition `blockgauge`.

## 2. Wasserstein (Kantorovich) Dobrushin uniqueness

- **The papers.**
  - The classical theory is due to Dobrushin (1968–70) and Föllmer (1982).
  - T. Dorlas, B. Savoie, *On the Wasserstein distance and the Dobrushin uniqueness theorem*, arXiv:2305.19371. The
    theorem for unbounded continuous spins, with W₁ completeness.
  - L. Wu, arXiv:math/0611635. Poincaré and transport inequalities under the Dobrushin condition.
  - C. Külske, F. Redig, arXiv:math-ph/0409061. The limits of the sup-norm condition for unbounded spins.
- **D5 and D7.** The cube condition is a W₁ Dobrushin–Shlosman block condition, so the comparison lemma
  (`lem:dscomparison`) is the consumer of D5. Wu's transport inequalities would turn the cube condition into
  concentration bounds, which is useful for D4-type mass estimates.
- **The Lean port (A4).** No formal W₁ Dobrushin theorem exists. Dorlas–Savoie is the cleanest modern source to
  formalise.

## 3. Bassalygo–Dobrushin and random environments

- **The papers.**
  - L. A. Bassalygo, R. L. Dobrushin, Theory Probab. Appl. 31 (1987) 572–589.
  - D. Kępa, Condens. Matter Phys. 11 (2008). The extension to continuous spins on irregular graphs.
  - Conache, Kondratiev, Kozitsky, Pasurek, arXiv:1501.00673. Dobrushin–Pechersky revisited: uniqueness and decay of
    correlations on general graphs with site-dependent, unbounded bounds.
- **D7, caveat 1 (annealed comparison).**
  - Bassalygo–Dobrushin is quenched: the bad set is fixed in advance.
  - The Dobrushin–Pechersky criterion allows site-dependent influence bounds controlled by an integrability condition
    on the spins. This is the closest existing statement to the *annealed* comparison we need.
  - **Concrete next step.** Restate the island bound (4.5β_W)^{4n} with a configuration-dependent bad set as a
    Dobrushin–Pechersky condition, where the "spin" is the local plaquette field and the integrability comes from D6.
- **Also.** A thesis of D. Putan (2014) has a section "Gibbs states on random configurations: annealed approach".
  *(unverified; table of contents only)*

## 4. Stochastic quantisation (Chandra–Chevyrev–Hairer–Shen)

- **The papers.**
  - A. Chandra, I. Chevyrev, M. Hairer, H. Shen, *Stochastic quantisation of Yang–Mills–Higgs in 3D*, Invent. Math. 237
    (2024) 541–696, arXiv:2201.03487. Local solutions, a gauge-covariant renormalisation, and a state space of gauge
    orbits with a Markov process.
  - I. Chevyrev, H. Shen, *Uniqueness of gauge covariant renormalisation of stochastic 3D YMH*, ARMA 250 (2026).
  - Chevyrev, J. Math. Phys. 63 (2022), a review. It notes that the 3D Yang–Mills measure is not constructed, even on the
    torus.
- **D4/D5/D7.** None directly: these works are dynamics at short times, not estimates on the Gibbs measure.
- **D8/(E).** The orbit space is the natural home for a continuum limit of the flowed observables (track B3, done in
  `slice/CCHS.md`). No 4D analogue exists; the 4D model is not subcritical.

## 5. Shen–Zhu–Zhu: Langevin and Bakry–Émery

- **The papers.**
  - H. Shen, R. Zhu, X. Zhu, *A stochastic analysis approach to lattice Yang–Mills at strong coupling*, CMP (2023),
    arXiv:2204.12737. Bakry–Émery ⇒ log-Sobolev and a mass gap for small β.
  - The same authors, *Langevin dynamics of lattice Yang–Mills–Higgs*, arXiv:2401.13299.
  - *U(N) lattice Yang–Mills in the 't Hooft regime*, arXiv:2510.22788, which combines a cluster expansion with a
    Langevin analysis of the SU(N) marginal. *(unverified authorship)*
- **D5.** The fibre-chart theorems use exactly this mechanism on the constrained fibre: Bakry–Émery/Brascamp–Lieb on a
  convex chart with λ large. The novelty in the forest paper is that the curvature is supplied by the constraint, so it
  holds at weak coupling on calm fibres. SZZ is the strong-coupling special case.
- **D7.** Bakry–Émery fails at large fields: the Hessian has negative directions at U_j = −1 (OPEN.md). Their results
  say nothing about large fields.
- **D4/D8.** No content.

## 6. Chatterjee and related probability

- **The papers.**
  - S. Chatterjee, *A probabilistic mechanism for quark confinement*, arXiv:2006.16229 (CMP 2021). A "strong mass gap",
    meaning exponential decay *under arbitrary boundary conditions*, implies the area law when the centre is
    nontrivial.
  - Chatterjee, *A scaling limit of SU(2) lattice Yang–Mills–Higgs*, arXiv:2401.10507.
  - Adhikari, Cao, *Correlation decay for finite lattice gauge theories at weak coupling*, arXiv:2202.10375 (Ann.
    Probab. 2025).
  - Cao, Park, Sheffield, *Random surfaces and lattice Yang–Mills*, Comm. AMS (2025), and the large-N surface sums,
    arXiv:2508.13827.
- **The supremum over boundary conditions.** It is exactly Chatterjee's notion. So (D), if proved, gives confinement
  for SU(N) by his theorem, at the same lattice scale.
- **D7.** Adhikari–Cao is the closest existing proof of the large fields being *harmless* at weak coupling: for finite
  groups the defects (vortices) are rare and are decoupled by a disagreement-percolation argument. `rare/RARE.md`
  showed that disagreement percolation fails for our continuous group. Their reduction of correlations to vortex
  clusters is still the template for Conjecture L.
- **D4/D5/D8.** No content.

## 7. mrdouglasny/LGT (Lean 4)

- Reservoir `@mrdouglasny/LGT`, github.com/mrdouglasny/lgt. U(n) Wilson lattice gauge theory on finite tori, with the
  Gibbs specification, DLR, Dobrushin verification and a strong-coupling mass gap with zero sorries (PR #2, May 2026).
  The condition is total variation and needs very small β (β_W < 0.0104 for the relevant case, per `A4_LEAN.md`).
  Built on Mathlib, `markov-semigroups` and `gaussian-field`.
- **For us.** A4 only. A W₁ Dobrushin theorem on top of it is the critical path to formalising the 0.351/0.77 results.
  Nothing for D4–D8.

## 8. 2025–2026 items

- **arXiv:2509.19176**, *Correlation decay for U(1) lattice Higgs theory: the case of small mass*. A gap for an abelian
  Higgs model for every small Higgs mass, at β large depending on m. It is a weak-coupling result with a mass term,
  i.e. the regime where the Gaussian benchmark of OPEN.md says the cube condition can hold. It is not pure Yang–Mills.
  *(authors unverified)*
- **arXiv:2509.03513** (rev. Jan 2026), on charge conjugation and Elitzur's theorem in SU(N), d = 4. It argues for a gap
  but states that it does not prove it. Nothing usable.
- **An alphaxiv listing dated October 2026** claims a volume-uniform gap in a strong-coupling window with a trivial
  continuum limit. *(unverified; not used)*
- I found no 2025–26 result that proves correlation decay for a continuous nonabelian group at weak coupling. The
  frontier for D7/D8 is still Bałaban (for the ultraviolet) and Adhikari–Cao (for finite groups).

## 9. What this means for the plan

- **D5.** Nothing in the literature is ahead of `chartdecay`. The step is a computation, done for calm data in
  `d5-calm/D5_CALM.md`.
- **D7.** Two concrete leads:
  - (a) Bałaban's per-cube large-field factor as the local rarity under any exterior;
  - (b) the Dobrushin–Pechersky criterion as the annealed comparison.

  Both should be tried on Conjecture L.
- **D8.** Bałaban/Dimock is the only route. Their constants are not explicit; ours are, but astronomically large.
- **D4.** No external tool found. It is the same multiscale problem.

## Sources

- [Dimock, RG according to Balaban I](https://arxiv.org/abs/1108.1335), [II](https://arxiv.org/abs/1212.5562), [III](https://arxiv.org/abs/1304.0705); [Covariant axial gauge](https://arxiv.org/abs/1410.2798); [QED on the 3-torus](https://arxiv.org/abs/math-ph/0210020); [UV regularity for QED d=3](https://arxiv.org/abs/1512.04373)
- [Dorlas–Savoie, Wasserstein distance and Dobrushin uniqueness](https://arxiv.org/abs/2305.19371); [Wu](https://arxiv.org/abs/math/0611635); [Külske–Redig](https://arxiv.org/abs/math-ph/0409061)
- [Bassalygo–Dobrushin (MathNet)](https://mathnet.ru/eng/tvp1676); [Kępa 2008](https://www.icmp.lviv.ua/journal/zbirnyk.54/010/abstract.html); [Conache–Kondratiev–Kozitsky–Pasurek](https://arxiv.org/abs/1501.00673); [Putan thesis](https://noah.nrw/ubbihs/content/structure/5129497)
- [CCHS, YMH in 3D](https://arxiv.org/abs/2201.03487); [Chevyrev–Shen (SISSA record)](https://iris.sissa.it/handle/20.500.11767/148650)
- [Shen–Zhu–Zhu strong coupling](https://arxiv.org/abs/2204.12737); [YMH Langevin](https://arxiv.org/abs/2401.13299); [U(N) 't Hooft regime review](https://www.themoonlight.io/review/mathrmun-lattice-yang-mills-in-the-t-hooft-regime)
- [Chatterjee, confinement](https://arxiv.org/abs/2006.16229); [Adhikari–Cao](https://arxiv.org/abs/2202.10375); [surface sums large N](https://arxiv.org/abs/2508.13827)
- [LGT on Reservoir](https://reservoir.lean-lang.org/@mrdouglasny/LGT)
- [U(1) Higgs small mass](https://arxiv.org/abs/2509.19176); [Charge conjugation SU(N)](https://arxiv.org/abs/2509.03513)
