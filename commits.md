<!--
 - SPDX-FileCopyrightText: 2021-2022 Union
 - SPDX-License-Identifier: MPL-2.0
 -->

## Branches

1. The `master` branch is only primary branch:
    1. The code in the `master` branch SHOULD always compile and pass all tests.
    2. The documentation in the `master` branch SHOULD always be up-to-date.

2. Issue branches:
    1. Naming scheme: `<username>/<issue_id>-<brief_description>`; in case there is no issue associated with a branch: `<username>/<brief_description>`.
    2. Make sure the description is really brief but clear enough so that it is easy to understand what the issue is about without looking it up in the issue tracker (assuming that you are familiar with existing issues).

    Examples:
    - `worm2fed/#1-example-issue`
    - `rexolion/#1234-ui-for-inputs`
    - `worm2fed/git-policy`

## Commit messages

1. We use [Conventional Commits](https://www.conventionalcommits.org/) approach, it provides an easy set of rules for creating an explicit commit history.

2. The commit message should be structured as follows:
    ```
    <type>([optional scope]): <description>

    [optional body]

    [optional footer(s)]
    ```

3. The commit contains the following structural elements, to communicate intent to the consumers:
    1. `fix`: a commit of the type fix patches a bug in your codebase (this correlates with PATCH in Semantic Versioning).
    2. `feat`: a commit of the type feat introduces a new feature to the codebase (this correlates with MINOR in Semantic Versioning).
    3. `BREAKING CHANGE`: a commit that has a footer BREAKING CHANGE:, or appends a `!` after the type/scope, introduces a breaking API change (correlating with MAJOR in Semantic Versioning). A `BREAKING CHANGE` can be part of commits of any type.
    4. Types other than `fix:` and `feat:` are allowed: `ci:`, `docs:`, `style:`, `refactor:` and `test:`.
    5. Footers other than BREAKING CHANGE: <description> may be provided and follow a convention similar to git trailer format.
    6. Additional types are not mandated by the Conventional Commits specification, and have no implicit effect in Semantic Versioning (unless they include a BREAKING CHANGE). A scope may be provided to a commit’s type, to provide additional contextual information and is contained within parenthesis, e.g., feat(parser): add ability to parse arrays.

## Pull requests

1. Each pull request SHOULD resolve exactly one issue.

2. Try to avoid too big PRs. If your PR has more than 500 additions + deletions, please think twice whether it can be split into smaller PRs.

3. PR title SHOULD adhere to the following scheme: `[ISSUE-ID] Brief description`; in case there is no issue associated with a PR: `[chore] Brief description`.

4. PR description MUST NOT be empty. If there is a PR template, PR description MUST adhere to this template. If there is no template, please describe the changes you've made and **why** you've made them. Also, provide links to related issues.

5. You SHOULD request a review from at least one person you think would be most suitable as reviewers. You MAY request a review from more people if the changes are substantial – use your discretion.

6. Upon submitting a pull request, ensure the commit history satisfies the following criteria:
    1. Each commit SHOULD be a minimal and accurate answer to exactly one identified and agreed problem.
    2. Each commit SHOULD NOT fix a problem introduced by an earlier commit in your pull request or revert an earlier commit in your PR (you can use fixups for that).
    3. Each commit SHOULD be signed.
    4. Your pull request generally shouldn't contain changes unrelated to the issue it solves. However, if you modify some file and see an obvious small mistake there (e. g. a typo or wrong formatting), you MAY fix it in your PR.

7. During the PR review:
    1. Make changes in separate commits, even if such commits do not comply with this policy.
    2. You MUST NOT amend the previous commits.
    3. You SHOULD use rebase to synchronize the branches, you SHOULD NOT use "Update branch" or merge to synchronize the branches unless rebasing is prohibitively hard.

8. After passing the review but before merging:
    1. Rebase your changes on the target branch.
    2. Use the interactive rebase to prettify the commit history so that it adheres to this policy.

9. Merging the changes:
    1. If you want to merge someone else's PR, you SHOULD make sure the author is fine with merging and does not want to do anything with the commit history.
    2. You MUST create a merge commit, i.e. you MUST NOT use neither fast-forward merge nor "squash and merge".
