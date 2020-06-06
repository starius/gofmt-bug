# gofmt-bug
go fmt ./... does not see files with tags in subpackages

```
$ git clone https://github.com/starius/gofmt-bug
$ cd gofmt-bug
$ go fmt ./...
$ go fmt ./bar
bar/bar.go
$ git diff
diff --git a/bar/bar.go b/bar/bar.go
index 6ee7dc6..faddbe5 100644
--- a/bar/bar.go
+++ b/bar/bar.go
@@ -2,5 +2,5 @@
 
 package bar
 
-func Bar(     ) {
+func Bar() {
 }
```

If there are files without tag in the same package, `go fmt ./...`
sees all the files and works as expected.
