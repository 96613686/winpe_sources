# Microsoft.Crm.Sandbox.SandboxWorkerManager::BackgroundThread

- ea: `0x6570`
- end: `0x65fb`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::BackgroundThread`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x6570`
- `0xc9e0`

## string_xrefs

- `0x6570`: `BackgroundThread`
- `0x65c2`: `SandboxWorkerManager.BackgroundThread: exit: BackgroundThread`
- `0x65da`: `SandboxWorkerManager.BackgroundThread: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x6570  ldstr    aBackgroundthre// "BackgroundThread"
0x6575  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(string)
0x657a  stloc.0
0x657b  newobj   instance void <>c__DisplayClass15_0::.ctor()
0x6580  stloc.1
0x6581  ldloc.1
0x6582  ldc.i4.0
0x6583  stfld    int32 <>c__DisplayClass15_0::loopCount
0x6588  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerManager::Logger
0x658d  newobj   instance void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmRootExecutionContext::.ctor()
0x6592  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class SandboxHostBackgroundThreadActivity>::get_Instance()
0x6597  ldloc.1
0x6598  ldfld    class [mscorlib]System.Func`1<bool> <>c__DisplayClass15_0::<>9__0
0x659d  dup
0x659e  brtrue.s loc_65B6
0x65a0  pop
0x65a1  ldloc.1
0x65a2  ldloc.1
0x65a3  ldftn    instance bool <>c__DisplayClass15_0::<BackgroundThread>b__0()
0x65a9  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x65ae  dup
0x65af  stloc.2
0x65b0  stfld    class [mscorlib]System.Func`1<bool> <>c__DisplayClass15_0::<>9__0
0x65b5  ldloc.2
0x65b6  call     T0x2B000007
0x65bb  brfalse.s loc_6588
0x65bd  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerManager::Logger
0x65c2  ldstr    aSandboxworkerm_6// "SandboxWorkerManager.BackgroundThread: "...
0x65c7  ldc.i4.0
0x65c8  newarr   [mscorlib]System.Object
0x65cd  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x65d2  leave.s  loc_65FA
0x65d4  stloc.3
0x65d5  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerManager::Logger
0x65da  ldstr    aSandboxworkerm_7// "SandboxWorkerManager.BackgroundThread: "...
0x65df  ldc.i4.1
0x65e0  newarr   [mscorlib]System.Object
0x65e5  dup
0x65e6  ldc.i4.0
0x65e7  ldloc.3
0x65e8  stelem.ref
0x65e9  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x65ee  rethrow
0x65f0  ldloc.0
0x65f1  brfalse.s loc_65F9
0x65f3  ldloc.0
0x65f4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65f9  endfinally
0x65fa  ret
```
