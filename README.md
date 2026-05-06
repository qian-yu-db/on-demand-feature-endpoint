# on-demand-feature-endpoint

Prototype comparing two serving shells for a CPU-only, regex/dict feature-engineering
transformer on Databricks: **Model Serving (MLflow pyfunc)** vs **Databricks Apps
(FastAPI + Gradio)**. Both tracks install the same `claims_fe` wheel, so any latency
or throughput delta reflects only the serving layer.

## Layout

- [`fe_endpoint_prototype/`](fe_endpoint_prototype/README.md) — end-to-end workflow:
  synthetic payloads → wheel build → deploy (pyfunc + app) → test → head-to-head
  comparison. Numbered notebooks `01_…06_` are the entry points.
- `pyproject.toml` / `uv.lock` — shared dev environment (managed with `uv`).

## Running the workflow

* Run the notebook 01 to 06 in a databricks workspace
* The `fe_endpoint_prototype/load_testing/` is for local testing

## Reference

* [Deploy and Query Databricks Model Serving](https://docs.databricks.com/aws/en/machine-learning/model-serving/model-serving-intro)
* [Set Up M2M OAuth](https://docs.databricks.com/aws/en/dev-tools/auth/oauth-m2m)
* [MLFlow Model](https://mlflow.org/docs/latest/ml/model/)
* [MLFlow From Code](https://mlflow.org/docs/latest/ml/model/models-from-code/)