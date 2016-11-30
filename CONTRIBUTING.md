# Contributing

## Workflow

We are using the [Feature Branch Workflow (also known as GitHub Flow)](https://guides.github.com/introduction/flow/), and prefer delivery as pull requests.

Our first line of defense is the [Travis CI](https://travis-ci.org/doorkeeper-gem/doorkeeper-openid_connect) build defined within [.travis.yml](.travis.yml) and triggered for every pull request.

Create a feature branch:

```sh
git checkout -B feat/contributing
```

## Creating Good Commits

The cardinal rule for creating good commits is to ensure there is only one
"logical change" per commit. Why is this an important rule?

* The smaller the amount of code being changed, the quicker & easier it is to
  review & identify potential flaws.

* If a change is found to be flawed later, it may be necessary to revert the
  broken commit. This is much easier to do if there are not other unrelated
  code changes entangled with the original commit.

* When troubleshooting problems using Git's bisect capability, small well
  defined changes will aid in isolating exactly where the code problem was
  introduced.

* When browsing history using Git annotate/blame, small well defined changes
  also aid in isolating exactly where & why a piece of code came from.

Things to avoid when creating commits:

* Mixing whitespace changes with functional code changes.
* Mixing two unrelated functional changes.
* Sending large new features in a single giant commit.

## Commit Message Conventions

We use commit messages as per [Conventional Changelog](https://github.com/conventional-changelog/conventional-changelog):

```none
<type>(<scope>): <subject>
```

Allowed types:

* **feat**: A new feature
* **fix**: A bug fix
* **docs**: Documentation only changes
* **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, newline, line endings, etc)
* **refactor**: A code change that neither fixes a bug or adds a feature
* **perf**: A code change that improves performance
* **test**: Adding missing tests
* **chore**: Changes to the build process or auxiliary tools and libraries such as documentation generation

You can add additional details after a new line to describe the change in detail or automatically close an issue on GitHub.

```none
feat: create initial CONTRIBUTING.md

This closes #73
```

## Release process

- Bump version in `lib/doorkeeper/openid_connect/version.rb`
- Update `CHANGELOG.md`
- Commit all changes
- Tag release and publish gem with `rake release`
