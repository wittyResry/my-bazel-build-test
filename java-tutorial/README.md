# Building a Java Project
```bash
brew install bazel
bazel build //:ProjectRunner
bazel-bin/ProjectRunner

output:
➜  java-tutorial git:(master) bazel build //:ProjectRunner
Extracting Bazel installation...
Starting local Bazel server and connecting to it...
.............
INFO: Analysed target //:ProjectRunner (15 packages loaded).
INFO: Found 1 target...
Target //:ProjectRunner up-to-date:
  bazel-bin/ProjectRunner.jar
    bazel-bin/ProjectRunner
    INFO: Elapsed time: 17.209s, Critical Path: 1.23s
    INFO: 2 processes: 1 local, 1 worker.
    INFO: Build completed successfully, 6 total actions
➜  java-tutorial git:(master) ✗ bazel-bin/ProjectRunner
Hi!
➜  java-tutorial git:(master) ✗ bazel query  --nohost_deps --noimplicit_deps 'deps(//:ProjectRunner)' --output graph
digraph mygraph {
  node [shape=box];
  "//:ProjectRunner"
  "//:ProjectRunner" -> "//:src/main/java/com/example/Greeting.java\n//:src/main/java/com/example/ProjectRunner.java"
  "//:src/main/java/com/example/Greeting.java\n//:src/main/java/com/example/ProjectRunner.java"
  }
```

