# <>c__DisplayClass14_0::<ScanWorkersThread>b__0

- ea: `0xc8a0`
- end: `0xc9c5`
- name: `<>c__DisplayClass14_0::<ScanWorkersThread>b__0`
- size: `293`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x48e0`
- `0x8040`
- `0xc8a0`

## string_xrefs

- `0xc8a5`: `SandboxWorkerManager.ScanWorkersThread: background thread sleeping: {0}`
- `0xc8e9`: `SandboxWorkerManager.ScanWorkersThread: _autoEventBackgroundThread signalled`
- `0xc909`: `SandboxWorkerManager.ScanWorkersThread: shutdown`
- `0xc920`: `SandboxWorkerManager.ScanWorkersThread: background thread wake up: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xc8a0  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerManager::Logger
0xc8a5  ldstr    aSandboxworkerm_105// "SandboxWorkerManager.ScanWorkersThread:"...
0xc8aa  ldc.i4.1
0xc8ab  newarr   [mscorlib]System.Object
0xc8b0  dup
0xc8b1  ldc.i4.0
0xc8b2  ldarg.0
0xc8b3  ldfld    int32 <>c__DisplayClass14_0::loopCount
0xc8b8  box      [mscorlib]System.Int32
0xc8bd  stelem.ref
0xc8be  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0xc8c3  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0xc8c8  ldc.i4.7
0xc8c9  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0xc8ce  stloc.0
0xc8cf  ldsfld   class [mscorlib]System.Threading.AutoResetEvent Microsoft.Crm.Sandbox.SandboxWorkerManager::_autoEventBackgroundThread
0xc8d4  ldc.i4.0
0xc8d5  ldc.i4.0
0xc8d6  ldloc.0
0xc8d7  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xc8dc  ldc.i4.0
0xc8dd  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(valuetype [mscorlib]System.TimeSpan, bool)
0xc8e2  brfalse.s loc_C91B
0xc8e4  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerManager::Logger
0xc8e9  ldstr    aSandboxworkerm_106// "SandboxWorkerManager.ScanWorkersThread:"...
0xc8ee  ldc.i4.0
0xc8ef  newarr   [mscorlib]System.Object
0xc8f4  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0xc8f9  volatile.
0xc8fb  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool Microsoft.Crm.Sandbox.SandboxWorkerManager::_shutdown
0xc900  brfalse.s loc_C943
0xc902  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc907  ldc.i4.s 0x21
0xc909  ldstr    aSandboxworkerm_107// "SandboxWorkerManager.ScanWorkersThread:"...
0xc90e  ldc.i4.0
0xc90f  newarr   [mscorlib]System.Object
0xc914  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xc919  ldc.i4.1
0xc91a  ret
0xc91b  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerManager::Logger
0xc920  ldstr    aSandboxworkerm_108// "SandboxWorkerManager.ScanWorkersThread:"...
0xc925  ldc.i4.1
0xc926  newarr   [mscorlib]System.Object
0xc92b  dup
0xc92c  ldc.i4.0
0xc92d  ldarg.0
0xc92e  ldfld    int32 <>c__DisplayClass14_0::loopCount
0xc933  box      [mscorlib]System.Int32
0xc938  stelem.ref
0xc939  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0xc93e  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::ScanWorkers()
0xc943  ldarg.0
0xc944  ldfld    int32 <>c__DisplayClass14_0::loopCount
0xc949  stloc.1
0xc94a  ldarg.0
0xc94b  ldloc.1
0xc94c  ldc.i4.1
0xc94d  add
0xc94e  stfld    int32 <>c__DisplayClass14_0::loopCount
0xc953  ldstr    aOrganizationma// "_organizationMap"
0xc958  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, bool>, class Microsoft.Crm.Sandbox.OrganizationWorkerList> Microsoft.Crm.Sandbox.SandboxWorkerManager::_organizationMap
0xc95d  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, bool>, class Microsoft.Crm.Sandbox.OrganizationWorkerList>::get_Count()
0xc962  stloc.1
0xc963  ldloca.s 1
0xc965  call     instance string [mscorlib]System.Int32::ToString()
0xc96a  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xc96f  ldstr    aProcesspool// "_processPool"
0xc974  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_processPool
0xc979  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Count()
0xc97e  stloc.1
0xc97f  ldloca.s 1
0xc981  call     instance string [mscorlib]System.Int32::ToString()
0xc986  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xc98b  ldstr    aCleannativepro// "_cleanNativeProcessQueue"
0xc990  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanNativeProcessQueue
0xc995  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0xc99a  stloc.1
0xc99b  ldloca.s 1
0xc99d  call     instance string [mscorlib]System.Int32::ToString()
0xc9a2  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xc9a7  ldstr    aCleandrawbridg// "_cleanDrawbridgeProcessQueue"
0xc9ac  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanDrawbridgeProcessQueue
0xc9b1  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0xc9b6  stloc.1
0xc9b7  ldloca.s 1
0xc9b9  call     instance string [mscorlib]System.Int32::ToString()
0xc9be  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xc9c3  ldc.i4.0
0xc9c4  ret
```
