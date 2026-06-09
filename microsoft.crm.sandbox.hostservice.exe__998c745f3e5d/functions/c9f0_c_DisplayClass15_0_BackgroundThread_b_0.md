# <>c__DisplayClass15_0::<BackgroundThread>b__0

- ea: `0xc9f0`
- end: `0xcba2`
- name: `<>c__DisplayClass15_0::<BackgroundThread>b__0`
- size: `434`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x3a20`
- `0x48e0`
- `0x6ad0`
- `0x6f40`
- `0x70f0`
- `0x7150`
- `0x88d0`
- `0xc9f0`

## string_xrefs

- `0xc9f5`: `SandboxWorkerManager.BackgroundThread: ----- background thread sleeping: {0}`
- `0xca39`: `SandboxWorkerManager.BackgroundThread: _autoEventBackgroundThread signalled`
- `0xca5a`: `SandboxWorkerManager.BackgroundThread: shutdown`
- `0xca71`: `SandboxWorkerManager.BackgroundThread: ----- background thread wake up: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xc9f0  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerManager::Logger
0xc9f5  ldstr    aSandboxworkerm_109// "SandboxWorkerManager.BackgroundThread: "...
0xc9fa  ldc.i4.1
0xc9fb  newarr   [mscorlib]System.Object
0xca00  dup
0xca01  ldc.i4.0
0xca02  ldarg.0
0xca03  ldfld    int32 <>c__DisplayClass15_0::loopCount
0xca08  box      [mscorlib]System.Int32
0xca0d  stelem.ref
0xca0e  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0xca13  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0xca18  ldc.i4.7
0xca19  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0xca1e  stloc.0
0xca1f  ldsfld   class [mscorlib]System.Threading.AutoResetEvent Microsoft.Crm.Sandbox.SandboxWorkerManager::_autoEventBackgroundThread
0xca24  ldc.i4.0
0xca25  ldc.i4.0
0xca26  ldloc.0
0xca27  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xca2c  ldc.i4.0
0xca2d  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(valuetype [mscorlib]System.TimeSpan, bool)
0xca32  brfalse.s loc_CA6C
0xca34  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerManager::Logger
0xca39  ldstr    aSandboxworkerm_110// "SandboxWorkerManager.BackgroundThread: "...
0xca3e  ldc.i4.0
0xca3f  newarr   [mscorlib]System.Object
0xca44  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0xca49  volatile.
0xca4b  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool Microsoft.Crm.Sandbox.SandboxWorkerManager::_shutdown
0xca50  brfalse  loc_CB20
0xca55  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerManager::Logger
0xca5a  ldstr    aSandboxworkerm_111// "SandboxWorkerManager.BackgroundThread: "...
0xca5f  ldc.i4.0
0xca60  newarr   [mscorlib]System.Object
0xca65  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0xca6a  ldc.i4.1
0xca6b  ret
0xca6c  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerManager::Logger
0xca71  ldstr    aSandboxworkerm_112// "SandboxWorkerManager.BackgroundThread: "...
0xca76  ldc.i4.1
0xca77  newarr   [mscorlib]System.Object
0xca7c  dup
0xca7d  ldc.i4.0
0xca7e  ldarg.0
0xca7f  ldfld    int32 <>c__DisplayClass15_0::loopCount
0xca84  box      [mscorlib]System.Int32
0xca89  stelem.ref
0xca8a  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0xca8f  ldc.i4.s 0x10
0xca91  ldarg.0
0xca92  ldfld    int32 <>c__DisplayClass15_0::loopCount
0xca97  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::CrashForWatson(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxProperty, int32)
0xca9c  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::CreateCleanWorkers()
0xcaa1  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::CleanupCrashFiles()
0xcaa6  ldsfld   class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanWorkerProcessTimer
0xcaab  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0xcab0  stloc.1
0xcab1  ldloca.s 1
0xcab3  call     instance int32 [mscorlib]System.TimeSpan::get_Minutes()
0xcab8  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanUnusedWorkerProcessFolderIntervalInMin
0xcabd  blt.s    loc_CAEA
0xcabf  ldsfld   class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanWorkerProcessTimer
0xcac4  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xcac9  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::CleanupOldWorkerProcessFolders()
0xcace  ldnull
0xcacf  ldftn    void Microsoft.Crm.Sandbox.SandboxWorkerManager::CleanupOrphanWorkerProcesses(object stateInfo)
0xcad5  newobj   instance void [mscorlib]System.Threading.WaitCallback::.ctor(object, native int)
0xcada  call     bool [mscorlib]System.Threading.ThreadPool::QueueUserWorkItem(class [mscorlib]System.Threading.WaitCallback)
0xcadf  pop
0xcae0  ldsfld   class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanWorkerProcessTimer
0xcae5  callvirt instance void [System]System.Diagnostics.Stopwatch::Restart()
0xcaea  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::CheckNumberOfWorkerProcesses()
0xcaef  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0xcaf4  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::PublishHostCounters(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration)
0xcaf9  call     void Microsoft.Crm.Sandbox.SandboxClientTracker::ExpireClients()
0xcafe  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::CheckServiceAccount()
0xcb03  ldarg.0
0xcb04  ldfld    int32 <>c__DisplayClass15_0::loopCount
0xcb09  ldc.i4.s 0xA
0xcb0b  rem
0xcb0c  brtrue.s loc_CB20
0xcb0e  ldnull
0xcb0f  ldftn    void Microsoft.Crm.Sandbox.SandboxWorkerManager::CleanupEmptyWorkerTraceFiles(object notUsed)
0xcb15  newobj   instance void [mscorlib]System.Threading.WaitCallback::.ctor(object, native int)
0xcb1a  call     bool [mscorlib]System.Threading.ThreadPool::QueueUserWorkItem(class [mscorlib]System.Threading.WaitCallback)
0xcb1f  pop
0xcb20  ldarg.0
0xcb21  ldfld    int32 <>c__DisplayClass15_0::loopCount
0xcb26  stloc.2
0xcb27  ldarg.0
0xcb28  ldloc.2
0xcb29  ldc.i4.1
0xcb2a  add
0xcb2b  stfld    int32 <>c__DisplayClass15_0::loopCount
0xcb30  ldstr    aOrganizationma// "_organizationMap"
0xcb35  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, bool>, class Microsoft.Crm.Sandbox.OrganizationWorkerList> Microsoft.Crm.Sandbox.SandboxWorkerManager::_organizationMap
0xcb3a  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, bool>, class Microsoft.Crm.Sandbox.OrganizationWorkerList>::get_Count()
0xcb3f  stloc.2
0xcb40  ldloca.s 2
0xcb42  call     instance string [mscorlib]System.Int32::ToString()
0xcb47  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xcb4c  ldstr    aProcesspool// "_processPool"
0xcb51  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_processPool
0xcb56  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Count()
0xcb5b  stloc.2
0xcb5c  ldloca.s 2
0xcb5e  call     instance string [mscorlib]System.Int32::ToString()
0xcb63  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xcb68  ldstr    aCleannativepro// "_cleanNativeProcessQueue"
0xcb6d  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanNativeProcessQueue
0xcb72  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0xcb77  stloc.2
0xcb78  ldloca.s 2
0xcb7a  call     instance string [mscorlib]System.Int32::ToString()
0xcb7f  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xcb84  ldstr    aCleandrawbridg// "_cleanDrawbridgeProcessQueue"
0xcb89  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanDrawbridgeProcessQueue
0xcb8e  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0xcb93  stloc.2
0xcb94  ldloca.s 2
0xcb96  call     instance string [mscorlib]System.Int32::ToString()
0xcb9b  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xcba0  ldc.i4.0
0xcba1  ret
```
