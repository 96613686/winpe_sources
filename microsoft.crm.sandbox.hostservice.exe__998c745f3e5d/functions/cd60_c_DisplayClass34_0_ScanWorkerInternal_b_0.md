# <>c__DisplayClass34_0::<ScanWorkerInternal>b__0

- ea: `0xcd60`
- end: `0xd0d3`
- name: `<>c__DisplayClass34_0::<ScanWorkerInternal>b__0`
- size: `883`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x5780`
- `0x8230`
- `0x85b0`
- `0x9720`
- `0x9730`
- `0x9770`
- `0x9780`
- `0x9790`
- `0x97e0`
- `0x9800`
- `0x9820`
- `0x9840`
- `0x9860`
- `0x98f0`
- `0x9930`
- `0x9de0`
- `0xa350`
- `0xcd60`

## string_xrefs

- `0xce79`: `SandboxWorkerManager.ScanWorkers:Thread[{0:d4}] HasExited returned Error {1}`

## pseudocode

```c

```

## disassembly

```asm
0xcd60  ldarg.0
0xcd61  ldflda   valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> <>c__DisplayClass34_0::kvp
0xcd66  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Value()
0xcd6b  stloc.0
0xcd6c  ldloc.0
0xcd6d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerId()
0xcd72  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(valuetype [mscorlib]System.Guid)
0xcd77  stloc.1
0xcd78  ldarg.0
0xcd79  ldflda   valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> <>c__DisplayClass34_0::kvp
0xcd7e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Key()
0xcd83  ldloc.0
0xcd84  callvirt instance class [System]System.Uri Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri()
0xcd89  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0xcd8e  ldstr    aSandboxworkerm_113// "SandboxWorkerManager.ScanWorkers: proce"...
0xcd93  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xcd98  ldloc.0
0xcd99  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xcd9e  stloc.2
0xcd9f  ldstr    aOrganizationid// "organizationId"
0xcda4  ldloc.0
0xcda5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xcdaa  stloc.s  4
0xcdac  ldloca.s 4
0xcdae  ldstr    aD// "D"
0xcdb3  call     instance string [mscorlib]System.Guid::ToString(string)
0xcdb8  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xcdbd  ldstr    aWorkerid// "workerId"
0xcdc2  ldloc.0
0xcdc3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerId()
0xcdc8  stloc.s  4
0xcdca  ldloca.s 4
0xcdcc  ldstr    aD// "D"
0xcdd1  call     instance string [mscorlib]System.Guid::ToString(string)
0xcdd6  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xcddb  ldstr    aWorkerstatus// "WorkerStatus"
0xcde0  ldloc.0
0xcde1  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerClient()
0xcde6  callvirt instance valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxWorkerClient::get_WorkerStatus()
0xcdeb  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus
0xcdf0  ldstr    aD// "D"
0xcdf5  call     instance string [mscorlib]System.Enum::ToString(string)
0xcdfa  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xcdff  ldloc.2
0xce00  ldc.i4.s 0x28
0xce02  ldstr    aSandboxworkerm_114// "SandboxWorkerManager.ScanWorkers: worke"...
0xce07  ldc.i4.1
0xce08  newarr   [mscorlib]System.Object
0xce0d  dup
0xce0e  ldc.i4.0
0xce0f  ldloc.0
0xce10  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0xce15  stelem.ref
0xce16  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xce1b  ldloc.0
0xce1c  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerClient()
0xce21  callvirt instance valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxWorkerClient::get_WorkerStatus()
0xce26  ldc.i4.4
0xce27  bne.un.s loc_CE59
0xce29  ldloc.0
0xce2a  ldc.i4.5
0xce2b  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::Exit(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason exitReason)
0xce30  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerManager::Logger
0xce35  ldstr    aSandboxworkerm_115// "SandboxWorkerManager.ScanWorkers: proce"...
0xce3a  ldc.i4.1
0xce3b  newarr   [mscorlib]System.Object
0xce40  dup
0xce41  ldc.i4.0
0xce42  ldloc.0
0xce43  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0xce48  stelem.ref
0xce49  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0xce4e  ldstr    aInvalidWorkerS// "Invalid worker status"
0xce53  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xce58  throw
0xce59  ldloc.0
0xce5a  callvirt instance class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerProcess()
0xce5f  callvirt instance void [System]System.Diagnostics.Process::Refresh()
0xce64  ldloc.0
0xce65  callvirt instance class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerProcess()
0xce6a  callvirt instance bool [System]System.Diagnostics.Process::get_HasExited()
0xce6f  stloc.3
0xce70  leave.s  loc_CEA7
0xce72  stloc.s  5
0xce74  ldloc.s  5
0xce76  ldloc.2
0xce77  ldc.i4.s 0x21
0xce79  ldstr    aSandboxworkerm_116// "SandboxWorkerManager.ScanWorkers:Thread"...
0xce7e  ldc.i4.2
0xce7f  newarr   [mscorlib]System.Object
0xce84  dup
0xce85  ldc.i4.0
0xce86  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xce8b  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0xce90  box      [mscorlib]System.Int32
0xce95  stelem.ref
0xce96  dup
0xce97  ldc.i4.1
0xce98  ldloc.s  5
0xce9a  callvirt instance string [mscorlib]System.Object::ToString()
0xce9f  stelem.ref
0xcea0  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcea5  rethrow
0xcea7  ldloc.3
0xcea8  brfalse.s loc_CED9
0xceaa  ldloc.0
0xceab  ldc.i4.5
0xceac  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::Exit(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason exitReason)
0xceb1  ldnull
0xceb2  ldloc.2
0xceb3  ldc.i4.s 0x28
0xceb5  ldstr    aSandboxworkerm_117// "SandboxWorkerManager.ScanWorkers: proce"...
0xceba  ldc.i4.1
0xcebb  newarr   [mscorlib]System.Object
0xcec0  dup
0xcec1  ldc.i4.0
0xcec2  ldloc.0
0xcec3  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0xcec8  stelem.ref
0xcec9  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcece  ldstr    aProcessHasExit// "Process has exited"
0xced3  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xced8  throw
0xced9  ldloc.0
0xceda  callvirt instance bool Microsoft.Crm.Sandbox.SandboxWorkerProcess::SnapshotResources()
0xcedf  brfalse  loc_D0C6
0xcee4  ldloc.2
0xcee5  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0xceea  ldloc.0
0xceeb  callvirt instance int64 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Memory()
0xcef0  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::MemoryUsage(int64)
0xcef5  ldloc.2
0xcef6  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0xcefb  ldloc.0
0xcefc  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Cpu()
0xcf01  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::ProcessorUsagePercent(int32)
0xcf06  ldloc.2
0xcf07  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0xcf0c  ldloc.0
0xcf0d  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_HandleCount()
0xcf12  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::HandleCount(int32)
0xcf17  ldarg.0
0xcf18  ldfld    bool <>c__DisplayClass34_0::isSandboxWorkerProcessAutodumpEnabled
0xcf1d  brfalse.s loc_CF25
0xcf1f  ldloc.0
0xcf20  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::CheckWorkerProcessForDump(class Microsoft.Crm.Sandbox.SandboxWorkerProcess workerProcess)
0xcf25  ldloc.0
0xcf26  ldarg.0
0xcf27  ldfld    int32 <>c__DisplayClass34_0::maxWorkerProcessMemoryLimitInMb
0xcf2c  ldarg.0
0xcf2d  ldfld    int32 <>c__DisplayClass34_0::maxWorkerProcessHandleCount
0xcf32  call     valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason Microsoft.Crm.Sandbox.SandboxWorkerManager::WorkerProcessExceedsResourceLimits(class Microsoft.Crm.Sandbox.SandboxWorkerProcess workerProcess, int32 maxWorkerProcessMemoryLimitPercentInMb, int32 maxWorkerProcessHandleCount)
0xcf37  stloc.s  6
0xcf39  ldstr    aResourceusagee// "resourceUsageExceededStatus"
0xcf3e  ldloc.s  6
0xcf40  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason
0xcf45  ldstr    aD// "D"
0xcf4a  call     instance string [mscorlib]System.Enum::ToString(string)
0xcf4f  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xcf54  ldloc.s  6
0xcf56  brfalse.s loc_CFCE
0xcf58  ldloc.0
0xcf59  ldloc.s  6
0xcf5b  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::Exit(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason exitReason)
0xcf60  ldnull
0xcf61  ldloc.2
0xcf62  ldc.i4.s 0x28
0xcf64  ldstr    aSandboxworkerm_118// "SandboxWorkerManager.ScanWorkers: proce"...
0xcf69  ldc.i4.6
0xcf6a  newarr   [mscorlib]System.Object
0xcf6f  dup
0xcf70  ldc.i4.0
0xcf71  ldloc.0
0xcf72  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_HandleCount()
0xcf77  box      [mscorlib]System.Int32
0xcf7c  stelem.ref
0xcf7d  dup
0xcf7e  ldc.i4.1
0xcf7f  ldarg.0
0xcf80  ldfld    int32 <>c__DisplayClass34_0::maxWorkerProcessHandleCount
0xcf85  box      [mscorlib]System.Int32
0xcf8a  stelem.ref
0xcf8b  dup
0xcf8c  ldc.i4.2
0xcf8d  ldloc.0
0xcf8e  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Cpu()
0xcf93  box      [mscorlib]System.Int32
0xcf98  stelem.ref
0xcf99  dup
0xcf9a  ldc.i4.3
0xcf9b  ldloc.0
0xcf9c  callvirt instance int64 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Memory()
0xcfa1  box      [mscorlib]System.Int64
0xcfa6  stelem.ref
0xcfa7  dup
0xcfa8  ldc.i4.4
0xcfa9  ldarg.0
0xcfaa  ldfld    int32 <>c__DisplayClass34_0::maxWorkerProcessMemoryLimitInMb
0xcfaf  box      [mscorlib]System.Int32
0xcfb4  stelem.ref
0xcfb5  dup
0xcfb6  ldc.i4.5
0xcfb7  ldloc.0
0xcfb8  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0xcfbd  stelem.ref
0xcfbe  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcfc3  ldstr    aResourceExceed// "Resource exceeded for process"
0xcfc8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xcfcd  throw
0xcfce  ldloc.0
0xcfcf  callvirt instance bool Microsoft.Crm.Sandbox.SandboxWorkerProcess::CanPingWorkerProcess()
0xcfd4  brtrue   loc_D07C
0xcfd9  ldc.i4.s 0xA
0xcfdb  ldc.i4.0
0xcfdc  call     T0x2B000001
0xcfe1  stloc.s  7
0xcfe3  ldloc.s  7
0xcfe5  brtrue   loc_D07C
0xcfea  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcfef  ldstr    a01// "{0}{1}"
0xcff4  ldc.i4.2
0xcff5  newarr   [mscorlib]System.Object
0xcffa  dup
0xcffb  ldc.i4.0
0xcffc  ldc.i4.2
0xcffd  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0xd002  stelem.ref
0xd003  dup
0xd004  ldc.i4.1
0xd005  ldc.i4.s 0x17
0xd007  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxProperty
0xd00c  stelem.ref
0xd00d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd012  ldc.i4.0
0xd013  box      [mscorlib]System.Int32
0xd018  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xd01d  unbox.any [mscorlib]System.Int32
0xd022  ldc.i4.0
0xd023  cgt
0xd025  brfalse.s loc_D02E
0xd027  ldloc.0
0xd028  ldc.i4.3
0xd029  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::Exit(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason exitReason)
0xd02e  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerManager::Logger
0xd033  ldstr    aSandboxworkerm_119// "SandboxWorkerManager.ScanWorkers: proce"...
0xd038  ldc.i4.4
0xd039  newarr   [mscorlib]System.Object
0xd03e  dup
0xd03f  ldc.i4.0
0xd040  ldloc.0
0xd041  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0xd046  stelem.ref
0xd047  dup
0xd048  ldc.i4.1
0xd049  ldloc.0
0xd04a  callvirt instance class [System]System.Uri Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri()
0xd04f  stelem.ref
0xd050  dup
0xd051  ldc.i4.2
0xd052  ldloc.0
0xd053  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_TotalActiveWorkerRequestCount()
0xd058  box      [mscorlib]System.Int32
0xd05d  stelem.ref
0xd05e  dup
0xd05f  ldc.i4.3
0xd060  ldloc.0
0xd061  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_TotalRequestsExecuted()
0xd066  box      [mscorlib]System.Int32
0xd06b  stelem.ref
0xd06c  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0xd071  ldstr    aFailedToPingWo// "Failed to ping worker process"
0xd076  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xd07b  throw
0xd07c  ldloc.0
0xd07d  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerClient()
0xd082  callvirt instance valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxWorkerClient::get_WorkerStatus()
0xd087  ldc.i4.5
0xd088  bne.un.s loc_D0B1
0xd08a  ldloc.0
0xd08b  ldc.i4.4
0xd08c  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::Exit(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason exitReason)
0xd091  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerManager::Logger
0xd096  ldstr    aSandboxworkerm_120// "SandboxWorkerManager.ScanWorkers: Worke"...
0xd09b  ldc.i4.1
0xd09c  newarr   [mscorlib]System.Object
0xd0a1  dup
0xd0a2  ldc.i4.0
0xd0a3  ldloc.0
0xd0a4  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0xd0a9  stelem.ref
0xd0aa  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0xd0af  leave.s  loc_D0D2
0xd0b1  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerManager::Logger
0xd0b6  ldstr    aSandboxworkerm_121// "SandboxWorkerManager.ScanWorkers: proce"...
0xd0bb  ldc.i4.0
0xd0bc  newarr   [mscorlib]System.Object
0xd0c1  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0xd0c6  leave.s  loc_D0D2
0xd0c8  ldloc.1
0xd0c9  brfalse.s loc_D0D1
  ... truncated ...
```
