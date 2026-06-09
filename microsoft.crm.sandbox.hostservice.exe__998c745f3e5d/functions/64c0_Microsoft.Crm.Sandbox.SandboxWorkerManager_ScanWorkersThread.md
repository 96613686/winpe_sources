# Microsoft.Crm.Sandbox.SandboxWorkerManager::ScanWorkersThread

- ea: `0x64c0`
- end: `0x6565`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::ScanWorkersThread`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x64c0`
- `0xc890`

## string_xrefs

- `0x64c0`: `ScanWorkersThread`
- `0x64d8`: `SandboxWorkerManager.ScanWorkersThread: started`
- `0x6529`: `SandboxWorkerManager.ScanWorkersThread: exit: BackgroundThread`
- `0x6544`: `SandboxWorkerManager.ScanWorkersThread: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x64c0  ldstr    aScanworkersthr// "ScanWorkersThread"
0x64c5  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(string)
0x64ca  stloc.0
0x64cb  newobj   instance void <>c__DisplayClass14_0::.ctor()
0x64d0  stloc.1
0x64d1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x64d6  ldc.i4.s 0x26
0x64d8  ldstr    aSandboxworkerm_3// "SandboxWorkerManager.ScanWorkersThread:"...
0x64dd  ldc.i4.0
0x64de  newarr   [mscorlib]System.Object
0x64e3  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x64e8  ldloc.1
0x64e9  ldc.i4.0
0x64ea  stfld    int32 <>c__DisplayClass14_0::loopCount
0x64ef  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerManager::Logger
0x64f4  newobj   instance void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmRootExecutionContext::.ctor()
0x64f9  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class ScanHostWorkersThreadActivity>::get_Instance()
0x64fe  ldloc.1
0x64ff  ldfld    class [mscorlib]System.Func`1<bool> <>c__DisplayClass14_0::<>9__0
0x6504  dup
0x6505  brtrue.s loc_651D
0x6507  pop
0x6508  ldloc.1
0x6509  ldloc.1
0x650a  ldftn    instance bool <>c__DisplayClass14_0::<ScanWorkersThread>b__0()
0x6510  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x6515  dup
0x6516  stloc.2
0x6517  stfld    class [mscorlib]System.Func`1<bool> <>c__DisplayClass14_0::<>9__0
0x651c  ldloc.2
0x651d  call     T0x2B000007
0x6522  brfalse.s loc_64EF
0x6524  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerManager::Logger
0x6529  ldstr    aSandboxworkerm_4// "SandboxWorkerManager.ScanWorkersThread:"...
0x652e  ldc.i4.0
0x652f  newarr   [mscorlib]System.Object
0x6534  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x6539  leave.s  loc_6564
0x653b  stloc.3
0x653c  ldloc.3
0x653d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6542  ldc.i4.s 0x26
0x6544  ldstr    aSandboxworkerm_5// "SandboxWorkerManager.ScanWorkersThread:"...
0x6549  ldc.i4.1
0x654a  newarr   [mscorlib]System.Object
0x654f  dup
0x6550  ldc.i4.0
0x6551  ldloc.3
0x6552  stelem.ref
0x6553  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6558  rethrow
0x655a  ldloc.0
0x655b  brfalse.s loc_6563
0x655d  ldloc.0
0x655e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6563  endfinally
0x6564  ret
```
