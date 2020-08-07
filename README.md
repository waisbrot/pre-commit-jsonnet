# Jsonnetfmt as a pre-commit hook

`jsonnetfmt` is a code-formatter that comes with [Jsonnet](https://jsonnet.org/).

[Pre-Commit](https://pre-commit.com/) is a library for creating and applying Git pre-commit hooks easily.

Together, you can automatically run `jsonnetfmt` before any commit, automatically.

## Installing

1. Get pre-commit: `pip install pre-commit`
2. Create a `.pre-commit.config.yaml` file in the root of your repository:
```yaml
---
repos:
    - repo: https://github.com/waisbrot/pre-commit-jsonnet.git
      rev: v1.0
      hooks:
          - id: jsonnetfmt
```
3. Install the hooks: `pre-commit install`
4. Commit code including a .jsonnet or .libsonnet file and it will run through `jsonnetfmt`
5. If the file was modified, `pre-commit` will abort the commit so you can check the changes. (`git diff` will show you changes between what you staged and what `jsonnetfmt` did.) Stage the modifications and commit again.
