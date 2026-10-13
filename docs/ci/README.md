# GitHub Actions CI 配置

```yaml
name: CI

on:
  push:
    branches: [ main, master ]
  pull_request:
    branches: [ main, master ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Structure check
        run: ls -la
```

## 使用方式

把上面的内容保存为 `.github/workflows/ci.yml` 即可生效。

> **注意**：GitHub 对 `.github/workflows/` 路径下的文件有权限要求
> （token 需要 `workflow` scope，或直接在网页上创建）。
> 这份文件放在 `docs/ci/github-actions.yml` 作为模板，
> 需要时复制到 `.github/workflows/ci.yml`。
