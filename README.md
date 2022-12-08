# Install Singularity Action

<img src="img/logo.png" alt="https://www.sylabs.io/guides/latest/user-guide" data-canonical-src="https://www.sylabs.io/guides/latest/user-guide" width="200" height="200">


## Usage

The action has the following variables:

| Name | Description | Required | Default |
|------|-------------|----------|---------|
|singularity-version | release version of [sylabs/singularity](https://github.com/sylabs/singularity/releases/) to install | false | 3.10.4 |
|go-version | version or range to provide to [actions/setup-go](https://github.com/actions/setup-go) | false | '>=1.17.0' |

And you can use as follows:

```yaml
name: Build Singularity
on:
  pull_request: []

jobs:
  install-singuarity:
    name: Install Singularity
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3
      - name: Singularity install with defaults
        uses: singularityhub/install-singularity@main

  install-singuarity-custom:
    name: Install Singularity Custom
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3
      - name: Singularity install with defaults
        uses: singularityhub/install-singularity@main
        with:
          singularity-version: 3.10.1
          go-version: 1.18.0
```

See the [action.yaml](action.yaml) for details.

**Note** that `singularity version` is currently outputting a hash, and it's unclear if this is a bug. I will
update it when I learn more (if there is a fix).
