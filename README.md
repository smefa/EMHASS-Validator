# EMHASS Runtime Parameter Validator

A single-file browser tool for validating `Passed runtime parameters` entries in your [EMHASS](https://emhass.readthedocs.io/en/latest/) logs.

## Usage

1. Download `emhass-log-validator.html`
2. Open it in any web browser — no server or internet connection required
3. To get the logs from MEHASS in Home Assistant go to Settings / Apps / EMAHSS / Logs
4. Paste your EMHASS log and click **Validate log**

## What it does

- Extracts all `Passed runtime parameters` blocks from the log
- Validates every parameter against the [EMHASS documentation](https://emhass.readthedocs.io/en/latest/passing_data.html)
- Shows **all** known parameters — both provided and missing — grouped by category
- Hover the **i** icon on any parameter to see full documentation, type and valid range
- Detects type errors, out-of-range values, mismatched array lengths and unknown parameters

## Checks performed

| Check | Example |
|---|---|
| Correct data type | Array, number, integer, boolean, string |
| Value range | SOC within 0–1, power values ≥ 0 |
| Forecast array length | Must match `prediction_horizon` |
| Deferrable load arrays | Length must match `number_of_deferrable_loads` |
| Cross-array consistency | All forecast arrays must have the same length |
| Unknown parameters | Warns if a key is not in the EMHASS docs |

## Privacy

All processing happens locally in your browser. Your log data is never sent anywhere.
