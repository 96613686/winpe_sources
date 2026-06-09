# <>c__DisplayClass72_0::<Execute>b__0

- ea: `0xd140`
- end: `0xd292`
- name: `<>c__DisplayClass72_0::<Execute>b__0`
- size: `338`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xd140`

## string_xrefs

- `0xd18b`: `WorkerCommunication`
- `0xd16e`: `PluginExecutionTimeout`

## pseudocode

```c

```

## disassembly

```asm
0xd140  ldarg.0
0xd141  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceSettings <>c__DisplayClass72_0::traceSettings
0xd146  ldc.i4.1
0xd147  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceSettings, bool)
0xd14c  stloc.0
0xd14d  ldarg.0
0xd14e  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext <>c__DisplayClass72_0::timeToStartTask
0xd153  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::Dispose()
0xd158  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xd15d  stloc.1
0xd15e  ldarg.0
0xd15f  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xd164  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass72_1::requestContext
0xd169  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_SharedVariables()
0xd16e  ldstr    aPluginexecutio// "PluginExecutionTimeout"
0xd173  ldc.i4.s 0x78
0xd175  box      [mscorlib]System.Int32
0xd17a  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xd17f  ldstr    aSandboxworkerp_58// "SandboxWorkerProcess.Execute.WCFCall"
0xd184  ldc.i4.3
0xd185  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0xd18a  stloc.2
0xd18b  ldstr    aWorkercommunic// "WorkerCommunication"
0xd190  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.ChaosAgent::ChaosClientCall(string)
0xd195  ldarg.0
0xd196  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xd19b  ldarg.0
0xd19c  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xd1a1  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient <>c__DisplayClass72_1::workerClient
0xd1a6  callvirt instance var<u1> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker>::get_Proxy()
0xd1ab  ldarg.0
0xd1ac  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xd1b1  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass72_1::newCallInfo
0xd1b6  ldarg.0
0xd1b7  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xd1bc  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass72_1::requestContext
0xd1c1  ldarg.0
0xd1c2  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xd1c7  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass72_1::pluginAssemblyId
0xd1cc  ldarg.0
0xd1cd  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xd1d2  ldfld    int32 <>c__DisplayClass72_1::sourceHash
0xd1d7  ldarg.0
0xd1d8  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xd1dd  ldfld    string <>c__DisplayClass72_1::assemblyName
0xd1e2  ldarg.0
0xd1e3  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xd1e8  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass72_1::pluginTypeId
0xd1ed  ldarg.0
0xd1ee  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xd1f3  ldfld    string <>c__DisplayClass72_1::pluginTypeName
0xd1f8  ldarg.0
0xd1f9  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xd1fe  ldfld    string <>c__DisplayClass72_1::pluginConfiguration
0xd203  ldarg.0
0xd204  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xd209  ldfld    string <>c__DisplayClass72_1::pluginSecureConfig
0xd20e  ldarg.0
0xd20f  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xd214  ldflda   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter <>c__DisplayClass72_1::workerCounter
0xd219  ldarg.0
0xd21a  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xd21f  ldfld    bool <>c__DisplayClass72_1::returnTraceInfo
0xd224  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker::Execute(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext, valuetype [mscorlib]System.Guid, int32, string, valuetype [mscorlib]System.Guid, string, string, string, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter&, bool)
0xd229  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass72_1::returnedContext
0xd22e  leave.s  loc_D23A
0xd230  ldloc.2
0xd231  brfalse.s loc_D239
0xd233  ldloc.2
0xd234  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd239  endfinally
0xd23a  ldarg.0
0xd23b  ldfld    class [mscorlib]System.Threading.AutoResetEvent <>c__DisplayClass72_0::ExecuteComplete
0xd240  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0xd245  pop
0xd246  ldloc.1
0xd247  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xd24c  ldarg.0
0xd24d  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xd252  ldfld    class [System]System.Diagnostics.Stopwatch <>c__DisplayClass72_1::taskStartStopwatch
0xd257  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xd25c  ldarg.0
0xd25d  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xd262  ldloc.1
0xd263  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xd268  stfld    int64 <>c__DisplayClass72_1::elapsedExecInMs
0xd26d  leave.s  loc_D279
0xd26f  ldloc.0
0xd270  brfalse.s loc_D278
0xd272  ldloc.0
0xd273  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd278  endfinally
0xd279  leave.s  loc_D291
0xd27b  stloc.3
0xd27c  ldarg.0
0xd27d  ldloc.3
0xd27e  stfld    class [mscorlib]System.Exception <>c__DisplayClass72_0::executeException
0xd283  ldarg.0
0xd284  ldfld    class [mscorlib]System.Threading.AutoResetEvent <>c__DisplayClass72_0::ExecuteComplete
0xd289  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0xd28e  pop
0xd28f  leave.s  loc_D291
0xd291  ret
```
