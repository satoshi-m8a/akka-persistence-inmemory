# akka-persistence-inmemory
Akka-persistence-inmemory is a plugin for [akka-persistence](http://doc.akka.io/docs/akka/snapshot/scala/persistence.html) 
that writes journal and snapshot entries entries to an in-memory store. It is very useful for testing your persistent actors.

[![Build Status](https://travis-ci.org/dnvriend/akka-persistence-inmemory.svg?branch=master)](https://travis-ci.org/dnvriend/akka-persistence-inmemory)

# Dependency
To include the plugin into your sbt project, add the following lines to your build.sbt file:

    resolvers += "dnvriend at bintray" at "http://dl.bintray.com/dnvriend/maven"

    libraryDependencies += "com.github.dnvriend" %% "akka-persistence-inmemory" % "1.0.2"

# Configuration
Add the following to the application.conf:

```
akka {
  persistence {
    journal.plugin = "inmemory-journal"
    snapshot-store.plugin = "inmemory-snapshot-store"
  }
}
```

## What's new?

## 1.0.3 (2015-05-25)
 - Merged Issue #2 [Sebastián Ortega](https://github.com/sortega) Regression: Fix corner case when persisted events are deleted, thanks!
 - Added test for the corner case issue #1 and #2

## 1.0.2 (2015-05-20)
 - Refactored from the ConcurrentHashMap implementation to a pure Actor managed concurrency model

## 1.0.1 (2015-05-16)
 - Some refactoring, fixed some misconceptions about the behavior of Scala Futures one year ago :)
 - Akka 2.3.6 -> 2.3.11
 - Scala 2.11.1 -> 2.11.6
 - Scala 2.10.4 -> 2.10.5
 - Merged Issue #1 [Sebastián Ortega](https://github.com/sortega) Fix corner case when persisted events are deleted, thanks!

## 1.0.0
 - Moved to bintray

## 0.0.2
 - Akka 2.3.4 -> 2.3.6

## 0.0.1
 - Initial Release

Have fun!