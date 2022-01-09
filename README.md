# Git Objects

## Show log
$ git log

## Show commit

$ git show --format=raw <commitish>

## Show tree

$ git ls-tree <treeish>

## show blob

$ git show <blob>
$ git cat-file blob <blob>

# Git GPG Signature

## Show Signatures in Log

$ git log --show-signatures

## Config to show signatures in log:

$ git config --global --add log.showSignature true

## Commit using GPG

$ git commit -S

## Config to Sign

$ git config --global commit.gpgsign true
$ git config --global user.signingkey ABCDEF02 <YOUR KEY>

## Add GPG-Public Key to Git

### Create Blob

$ gpg -a --export <YOUR KEY> | git hash-object -w --stdin 

### Add Tag to Blob

$ git tag -s MY_KEY <blob-hash>

### Verify

$ git tag -v MY_KEY

### Push to repo
 
$ git push --tags

