# gradle-scala-plugin-zinc-error
This is project created to replicate my inability to set up project with zinc 2.12

## Error

to replicate error run this command: `./gradlew run`

### With zinc set to 2.12

gradle file:

```gradle
dependencies {
    zinc "org.scala-sbt:zinc_2.12:1.6.1"
    implementation 'org.scala-lang:scala-library:2.12.15'
}
```

```
> Task :app:compileScala FAILED
## Exception when compiling 1 sources to /Users/tomasmazvila/Documents/Programming/test-gradle-plugin/app/build/classes/scala/main
java.lang.NoClassDefFoundError: scala/jdk/javaapi/CollectionConverters
org.gradle.api.internal.tasks.scala.TimeCheckingClassLoaderCache.cachedCustomClassloader(TimeCheckingClassLoaderCache.java:101)
sbt.internal.inc.classpath.ClassLoaderCache.cachedCustomClassloader(ClassLoaderCache.scala:57)
sbt.internal.inc.AnalyzingCompiler.getDualLoader(AnalyzingCompiler.scala:365)
sbt.internal.inc.AnalyzingCompiler.getCompilerLoader(AnalyzingCompiler.scala:343)
sbt.internal.inc.AnalyzingCompiler.compile(AnalyzingCompiler.scala:87)
sbt.internal.inc.MixedAnalyzingCompiler.$anonfun$compile$7(MixedAnalyzingCompiler.scala:192)
scala.runtime.java8.JFunction0$mcV$sp.apply(JFunction0$mcV$sp.java:23)
sbt.internal.inc.MixedAnalyzingCompiler.timed(MixedAnalyzingCompiler.scala:247)
sbt.internal.inc.MixedAnalyzingCompiler.$anonfun$compile$4(MixedAnalyzingCompiler.scala:182)
sbt.internal.inc.MixedAnalyzingCompiler.$anonfun$compile$4$adapted(MixedAnalyzingCompiler.scala:163)
sbt.internal.inc.JarUtils$.withPreviousJar(JarUtils.scala:239)
sbt.internal.inc.MixedAnalyzingCompiler.compileScala$1(MixedAnalyzingCompiler.scala:163)
sbt.internal.inc.MixedAnalyzingCompiler.compile(MixedAnalyzingCompiler.scala:210)
sbt.internal.inc.IncrementalCompilerImpl.$anonfun$compileInternal$1(IncrementalCompilerImpl.scala:528)
sbt.internal.inc.IncrementalCompilerImpl.$anonfun$compileInternal$1$adapted(IncrementalCompilerImpl.scala:528)
sbt.internal.inc.Incremental$.$anonfun$apply$5(Incremental.scala:177)
sbt.internal.inc.Incremental$.$anonfun$apply$5$adapted(Incremental.scala:175)
sbt.internal.inc.Incremental$$anon$2.run(Incremental.scala:461)
sbt.internal.inc.IncrementalCommon$CycleState.next(IncrementalCommon.scala:116)
sbt.internal.inc.IncrementalCommon$$anon$1.next(IncrementalCommon.scala:56)
sbt.internal.inc.IncrementalCommon$$anon$1.next(IncrementalCommon.scala:52)
sbt.internal.inc.IncrementalCommon.cycle(IncrementalCommon.scala:263)
sbt.internal.inc.Incremental$.$anonfun$incrementalCompile$8(Incremental.scala:416)
sbt.internal.inc.Incremental$.withClassfileManager(Incremental.scala:503)
sbt.internal.inc.Incremental$.incrementalCompile(Incremental.scala:403)
sbt.internal.inc.Incremental$.apply(Incremental.scala:169)
sbt.internal.inc.IncrementalCompilerImpl.compileInternal(IncrementalCompilerImpl.scala:528)
sbt.internal.inc.IncrementalCompilerImpl.$anonfun$compileIncrementally$1(IncrementalCompilerImpl.scala:482)
sbt.internal.inc.IncrementalCompilerImpl.handleCompilationError(IncrementalCompilerImpl.scala:332)
sbt.internal.inc.IncrementalCompilerImpl.compileIncrementally(IncrementalCompilerImpl.scala:420)
sbt.internal.inc.IncrementalCompilerImpl.compile(IncrementalCompilerImpl.scala:137)
org.gradle.api.internal.tasks.scala.ZincScalaCompiler.execute(ZincScalaCompiler.java:170)
org.gradle.api.internal.tasks.scala.ZincScalaCompilerFacade.execute(ZincScalaCompilerFacade.java:47)
org.gradle.api.internal.tasks.scala.ZincScalaCompilerFacade.execute(ZincScalaCompilerFacade.java:32)
org.gradle.api.internal.tasks.compile.daemon.AbstractDaemonCompiler$CompilerWorkAction.execute(AbstractDaemonCompiler.java:135)                                                                                                         [7/47]
org.gradle.workers.internal.DefaultWorkerServer.execute(DefaultWorkerServer.java:63)
org.gradle.workers.internal.AbstractClassLoaderWorker$1.create(AbstractClassLoaderWorker.java:49)
org.gradle.workers.internal.AbstractClassLoaderWorker$1.create(AbstractClassLoaderWorker.java:43)
org.gradle.internal.classloader.ClassLoaderUtils.executeInClassloader(ClassLoaderUtils.java:100)
org.gradle.workers.internal.AbstractClassLoaderWorker.executeInClassLoader(AbstractClassLoaderWorker.java:43)
org.gradle.workers.internal.IsolatedClassloaderWorker.run(IsolatedClassloaderWorker.java:49)
org.gradle.workers.internal.IsolatedClassloaderWorker.run(IsolatedClassloaderWorker.java:30)
org.gradle.workers.internal.WorkerDaemonServer.run(WorkerDaemonServer.java:87)
org.gradle.workers.internal.WorkerDaemonServer.run(WorkerDaemonServer.java:56)
org.gradle.process.internal.worker.request.WorkerAction$1.call(WorkerAction.java:138)
org.gradle.process.internal.worker.child.WorkerLogEventListener.withWorkerLoggingProtocol(WorkerLogEventListener.java:41)
org.gradle.process.internal.worker.request.WorkerAction.run(WorkerAction.java:135)
java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
java.base/java.lang.reflect.Method.invoke(Method.java:566)
org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:36)
org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:24)
org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:182)
org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:164)
org.gradle.internal.remote.internal.hub.MessageHub$Handler.run(MessageHub.java:414)
org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:64)
org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:48)
java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1128)
java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:628)
java.base/java.lang.Thread.run(Thread.java:829)


FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':app:compileScala'.
> scala/jdk/javaapi/CollectionConverters

* Try:
> Run with --stacktrace option to get the stack trace.
> Run with --info or --debug option to get more log output.
> Run with --scan to get full insights.

* Get more help at https://help.gradle.org

BUILD FAILED in 1s
1 actionable task: 1 executed
```

### Without zinc set to 2.12

gradle file:

```gradle
dependencies {
    // zinc "org.scala-sbt:zinc_2.12:1.6.1" <- No zinc set!
    implementation 'org.scala-lang:scala-library:2.12.15'
}
```

```
> Task :app:compileScala FAILED

FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':app:compileScala'.
> The version of 'scala-library' was changed while using the default Zinc version. Version 2.12.15 is not compatible with org.scala-sbt:zinc_2.13:1.6.1

* Try:
> Run with --stacktrace option to get the stack trace.
> Run with --info or --debug option to get more log output.
> Run with --scan to get full insights.

* Get more help at https://help.gradle.org

BUILD FAILED in 518ms
1 actionable task: 1 executed
```
