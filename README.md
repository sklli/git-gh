Github extensions for Git
=======

To install:

First, install node.js (at least 0.8).

```
(sudo) npm install -g git-gh
git ghsetup
```

And follow the prompts. Your password is never saved. You can see the config file .gitgh in your home directory if you don't believe me.

Commands
========

```
git list [filter]
```

List open issues and pull requests. The "filter" parameter can be any of the following
* all
* prs - only show pull requests
* issues - only show issues
* mine - only items that are assigned to you
* unassigned - only items that are unassigned
* milestone x - only items that are associated with milestone "x" (this can be any number of words, but is case insensitive)

```
git detail <id>
```

Get detail on issue/pull request with the given id

```
git claim <id>
```

Assign the given issue/pull request to yourself

```
git assign <id> <username>
```

Assign the given issue/pull request to username

```
git issue [-t 'title for issue'] [-m 'body of issue']
```

Open a new issue, if a title is not specified one will be generated by truncating the body. If a body is not specified, your default editor (or vim if $EDITOR is unset) will open with a temporary file. Whatever you save to that file will become the message body.

```
git pr [branch] [-t 'title for pull request'] [-m 'body of pull request']
```

Open a new pull request. The "branch" parameter is the branch you'd like your current branch to be merged into. The title will be set to "Merge yourbranch" if unspecified, and an editor will be spawned for you to specify a body much as the above issue command.

```
git comment <id> [-m 'your comment body']
```

Comment on issue/pull request id, if no message body is specified an editor will be spawned for you to type one in

```
git close <id>
```

Close the issue/pull request. This will *not* merge a pull request.