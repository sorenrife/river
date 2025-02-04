# Unreleased

- Moved all metrics in `metrics.cluster` except `metrics.Silhouette` to [river-extra](https://github.com/online-ml/river-extra).

## dist

- A `revert` method has been added to `stats.Gaussian`.
- A `revert` method has been added to `stats.Multinomial`.
- Added `dist.TimeRolling` to measure probability distributions over windows of time.

## drift

- Add the `PeriodicTrigger` detector, a baseline capable of producing drift signals in regular or random intervals.
- The numpy usage was removed in `drift.KSWIN` in favor of `collections.deque`. Appending or deleting elements to numpy arrays imply creating another object.
- Added the seed parameter to `drift.KSWIN` to control reproducibility.
- The Kolmogorov-Smirnov test mode was changed to the default (`"auto"`) to suppress warnings (`drift.KSWIN`).
- Unnecessary usage of numpy was also removed in other concept drift detectors.

## ensemble

- Streamline `SRP{Classifier,Regressor}`, remove unneeded numpy usage, make SRP variants robust against missing features, and fix bugs.
- Remove unneeded numpy usage `AdaptiveRandomForest{Classifier,Regressor}`.

## evaluate

- Added a `iter_progressive_val_score` function, which does the same as `progressive_val_score`, except that it yields rather than prints results at each step, which give more control to the user.

## imblearn

- Added `imblearn.ChebyshevUnderSampler` and `imblearn.ChebyshevOverSampler` for imbalanced regression.

## linear_model

- `linear_model.LinearRegression` and `linear_model.LogisticRegression` now correctly apply the `l2` regularization when their `learn_many` method is used.
- Added `l1` regularization (implementation with cumulative penalty, see [paper](https://aclanthology.org/P09-1054/)) for `linear_model.LinearRegression` and `linear_model.LogisticRegression`

## rules

- AMRules's `debug_one` explicitly indicates the prediction strategy used by each rule.
- Fix bug in `debug_one` (AMRules) where prediction explanations were incorrectly displayed when `ordered_rule_set=True`.

## tree
- Fix bug in Naive Bayes-based leaf prediction.
- Remove unneeded numpy usage in `HoeffdingAdaptiveTree{Classifier,Regressor}`.

## stats

- A `revert` method has been added to `stats.Var`.
