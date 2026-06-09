# Microsoft.Crm.Sandbox.SandboxWorkerProcess::.ctor

- ea: `0x9640`
- end: `0x9719`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::.ctor`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x5980`
- `0x8df0`

## callees

- `0x48e0`
- `0x5930`
- `0x9640`

## string_xrefs

- `0x9708`: `SandboxWorkerProcess.SandboxWorkerProcess: SandboxProperty.DisableNativeMethodCreate is on. The default value should be off.`

## pseudocode

```c

```

## disassembly

```asm
0x9640  ldarg.0
0x9641  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x9646  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerId
0x964b  ldarg.0
0x964c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9651  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::_organizationId
0x9656  ldarg.0
0x9657  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x965c  stloc.0
0x965d  ldloca.s 0
0x965f  ldstr    aB// "B"
0x9664  call     instance string [mscorlib]System.Guid::ToString(string)
0x9669  stfld    string Microsoft.Crm.Sandbox.SandboxWorkerProcess::_fullId
0x966e  ldarg.0
0x966f  newobj   instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::.ctor()
0x9674  stfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0x9679  ldarg.0
0x967a  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::.ctor()
0x967f  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerExecutionRecord
0x9684  ldarg.0
0x9685  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord>::.ctor()
0x968a  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord> Microsoft.Crm.Sandbox.SandboxWorkerProcess::_dictionaryPluginExecutionRecords
0x968f  ldarg.0
0x9690  newobj   instance void [System.Core]System.Threading.ReaderWriterLockSlim::.ctor()
0x9695  stfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxWorkerProcess::_dictionaryLock
0x969a  ldarg.0
0x969b  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x96a0  ldc.i4.s 0xA
0x96a2  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x96a7  stfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_operationTimeoutInSec
0x96ac  ldarg.0
0x96ad  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x96b2  stfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Sandbox.SandboxWorkerProcess::_totalTime
0x96b7  ldarg.0
0x96b8  call     class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmLoggerFactory::get_LoggerFactory()
0x96bd  ldtoken  Microsoft.Crm.Sandbox.SandboxWorkerProcess
0x96c2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x96c7  callvirt instance string [mscorlib]System.Type::get_Namespace()
0x96cc  callvirt instance class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory::CreateLogger(string)
0x96d1  stfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerProcess::Logger
0x96d6  ldarg.0
0x96d7  call     instance void [mscorlib]System.Object::.ctor()
0x96dc  ldarg.0
0x96dd  ldarg.1
0x96de  stfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::WorkerPort
0x96e3  ldarg.0
0x96e4  ldarg.2
0x96e5  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<int32> Microsoft.Crm.Sandbox.SandboxWorkerProcess::_portsQueue
0x96ea  ldarg.0
0x96eb  ldc.i4.s 0x15
0x96ed  ldc.i4.0
0x96ee  call     T0x2B000001
0x96f3  stfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::DisableNativeMethodCreate
0x96f8  ldarg.0
0x96f9  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::DisableNativeMethodCreate
0x96fe  ldc.i4.0
0x96ff  ble.s    loc_9718
0x9701  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9706  ldc.i4.s 0x21
0x9708  ldstr    aSandboxworkerp_3// "SandboxWorkerProcess.SandboxWorkerProce"...
0x970d  ldc.i4.0
0x970e  newarr   [mscorlib]System.Object
0x9713  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9718  ret
```
