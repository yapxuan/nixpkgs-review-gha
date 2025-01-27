# nixpkgs-review-gha

Run [nixpkgs-review](https://github.com/Mic92/nixpkgs-review) in GitHub Actions

## Features
- Build on `x86_64-linux`, `aarch64-linux`, `x86_64-darwin` and `aarch64-darwin`
- No local setup
- Automatically post results on the reviewed pull request
- Wait for [upstream evaluation](https://github.com/NixOS/nixpkgs/blob/master/.github/workflows/eval.yml) to finish before running nixpkgs-review
- Optionally start a [tmate](https://tmate.io/) session after nixpkgs-review has finished to allow interactive testing/debugging via SSH

## Setup
1. [Fork](https://github.com/Defelo/nixpkgs-review-gha/fork) this repository.
2. In your fork, go to the [Actions](../../actions) tab and enable GitHub Actions workflows.
3. (optional) If you want nixpkgs-review-gha to automatically post the results on the reviewed pull requests, you need to generate a [personal access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens):
    1. Go to <https://github.com/settings/tokens> and generate a new **classic** token with the `public_repo` scope.
    2. In your fork, go to "Settings" > "Secrets and variables" > "actions" and [add a new repository secret](../../settings/secrets/actions/new):
        - name: `GH_TOKEN`
        - value: the personal access token you generated before

## Usage
1. Open the [review workflow in the "Actions" tab](../../actions/workflows/review.yml)
2. Click on "Run workflow"
3. Enter the number of the pull request in nixpkgs you would like to review and click on "Run workflow"
4. Reload the page if necessary and click on the review run to see the logs
