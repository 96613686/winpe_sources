# Microsoft.Crm.Sandbox.SandboxWorkerManager::CreateNewWorkerProcess

- ea: `0x74f0`
- end: `0x7602`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::CreateNewWorkerProcess`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xccb0`

## callees

- `0x48e0`
- `0x74f0`
- `0x7df0`

## string_xrefs

- `0x7505`: `SandboxWorkerManager.CreateNewWorkerProcess:Thread[{0:d4}]: Unable to get a clean workerprocess from queue. Enqueuing a new AddWorker with UseDrawbridge: {1}. Number of clean Drawbridge process: {2}. Number of Drawbridge Processes to be initialized: {3}. Number of clean Native Process: {4}. Number of Native Process to be initialized: {5}.`
- `0x7599`: `SandboxWorkerManager.CreateNewWorkerProcess:Thread[{0:d4}]: Wait released in {1} secs!!!`
- `0x75d6`: `SandboxWorkerManager.CreateNewWorkerProcess:Thread[{0:d4}]: Wait timeout after {1} ms!!!`

## pseudocode

```c

```

## disassembly

```asm
0x74f0  ldc.i4.0
0x74f1  newobj   instance void [mscorlib]System.Threading.AutoResetEvent::.ctor(bool)
0x74f6  stloc.0
0x74f7  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [mscorlib]System.Threading.AutoResetEvent> Microsoft.Crm.Sandbox.SandboxWorkerManager::_autoEventWorkerAvailable
0x74fc  ldloc.0
0x74fd  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [mscorlib]System.Threading.AutoResetEvent>::Enqueue(var<u1>)
0x7502  ldarg.0
0x7503  ldc.i4.s 0x21
0x7505  ldstr    aSandboxworkerm_48// "SandboxWorkerManager.CreateNewWorkerPro"...
0x750a  ldc.i4.6
0x750b  newarr   [mscorlib]System.Object
0x7510  dup
0x7511  ldc.i4.0
0x7512  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x7517  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x751c  box      [mscorlib]System.Int32
0x7521  stelem.ref
0x7522  dup
0x7523  ldc.i4.1
0x7524  ldarg.1
0x7525  box      [mscorlib]System.Boolean
0x752a  stelem.ref
0x752b  dup
0x752c  ldc.i4.2
0x752d  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanDrawbridgeProcessQueue
0x7532  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0x7537  box      [mscorlib]System.Int32
0x753c  stelem.ref
0x753d  dup
0x753e  ldc.i4.3
0x753f  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_waitingStartupDrawbridgeProcess
0x7544  box      [mscorlib]System.Int32
0x7549  stelem.ref
0x754a  dup
0x754b  ldc.i4.4
0x754c  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanNativeProcessQueue
0x7551  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0x7556  box      [mscorlib]System.Int32
0x755b  stelem.ref
0x755c  dup
0x755d  ldc.i4.5
0x755e  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_waitingStartupNativeProcess
0x7563  box      [mscorlib]System.Int32
0x7568  stelem.ref
0x7569  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x756e  ldarg.1
0x756f  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::BackgroundCreateNewWorkerProcess(bool useDrawbridgeIsolation)
0x7574  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x7579  ldc.i4.6
0x757a  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x757f  stloc.1
0x7580  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x7585  stloc.2
0x7586  ldloc.0
0x7587  ldloc.1
0x7588  ldc.i4.0
0x7589  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(int32, bool)
0x758e  brfalse.s loc_75D2
0x7590  ldloc.2
0x7591  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x7596  ldarg.0
0x7597  ldc.i4.s 0x21
0x7599  ldstr    aSandboxworkerm_49// "SandboxWorkerManager.CreateNewWorkerPro"...
0x759e  ldc.i4.2
0x759f  newarr   [mscorlib]System.Object
0x75a4  dup
0x75a5  ldc.i4.0
0x75a6  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x75ab  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x75b0  box      [mscorlib]System.Int32
0x75b5  stelem.ref
0x75b6  dup
0x75b7  ldc.i4.1
0x75b8  ldloc.2
0x75b9  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x75be  stloc.3
0x75bf  ldloca.s 3
0x75c1  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x75c6  box      [mscorlib]System.Double
0x75cb  stelem.ref
0x75cc  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x75d1  ret
0x75d2  ldnull
0x75d3  ldarg.0
0x75d4  ldc.i4.s 0x21
0x75d6  ldstr    aSandboxworkerm_50// "SandboxWorkerManager.CreateNewWorkerPro"...
0x75db  ldc.i4.2
0x75dc  newarr   [mscorlib]System.Object
0x75e1  dup
0x75e2  ldc.i4.0
0x75e3  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x75e8  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x75ed  box      [mscorlib]System.Int32
0x75f2  stelem.ref
0x75f3  dup
0x75f4  ldc.i4.1
0x75f5  ldloc.1
0x75f6  box      [mscorlib]System.Int32
0x75fb  stelem.ref
0x75fc  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7601  ret
```
