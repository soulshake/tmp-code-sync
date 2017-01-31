# Steps to reproduce

Run `convox start` and modify a file within `./subdir/foo` (which is present in `.dockerignore`).

```
$ convox start
build  │ running: docker build -f /home/aj/git/convox/support/code-sync/Dockerfile -t code-sync/test /home/aj/git/convox/support/code-sync
build  │ Sending build context to Docker daemon  47.1 kB
build  │ Step 1/2 : FROM alpine
build  │  ---> ee4603260daa
build  │ Step 2/2 : ADD subdir /subdir
build  │  ---> 949ec0c10992
build  │ Removing intermediate container 814a6b85b54e
build  │ Successfully built 949ec0c10992
test   │ running: docker run -i --rm --name code-sync-test code-sync/test sh -c sleep 999
convox │ 1 files uploaded
convox │ -> /home/aj/git/convox/support/code-sync/subdir/a
convox │ 1 files uploaded
convox │ -> /home/aj/git/convox/support/code-sync/subdir/foo/c
```
