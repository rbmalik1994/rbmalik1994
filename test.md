test for git 
test 1

Note: Encountered an error when trying to create a new branch:
```
```shell
git checkout -b apps/test/featute/test1
fatal: cannot lock ref 'refs/heads/apps/test/featute/test1': 'refs/heads/apps/test' exists; cannot create 'refs/heads/apps/test/featute/test1'
```


Finish feature
```sh
#!/bin/bash
# Finish a feature and merge it into dev
feature_name=$1

if [ -z "$feature_name" ]; then
    echo "Please provide a feature name."
    exit 1
fi

git checkout feature/$feature_name
git pull origin feature/$feature_name
git checkout dev
git merge --no-ff feature/$feature_name
git branch -d feature/$feature_name
git push origin dev
echo "Feature $feature_name finished and merged into dev."
```

New Branch 

```sh
#!/bin/bash
# Start a new feature
feature_name=$1

if [ -z "$feature_name" ]; then
    echo "Please provide a feature name."
    exit 1
fi

git checkout dev
git pull origin dev
git checkout -b feature/$feature_name
echo "Started feature branch: feature/$feature_name"
```

test 4