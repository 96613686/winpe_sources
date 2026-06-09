# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::.cctor

- ea: `0x4c30`
- end: `0x4cd8`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::.cctor`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## string_xrefs

- `0x4c30`: `SandboxWorkerTracingBasePath`
- `0x4c7d`: `threadId`
- `0x4c85`: `processId`

## pseudocode

```c

```

## disassembly

```asm
0x4c30  ldstr    aSandboxworkert// "SandboxWorkerTracingBasePath"
0x4c35  ldstr    aCCrmtrace// "C:\\CrmTrace\\"
0x4c3a  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x4c3f  castclass [mscorlib]System.String
0x4c44  stsfld   string Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::basePath
0x4c49  ldstr    aSandboxworkerc// "SandboxWorkerConsoleTracingEnabled"
0x4c4e  ldc.i4.0
0x4c4f  box      [mscorlib]System.Int32
0x4c54  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x4c59  unbox.any [mscorlib]System.Int32
0x4c5e  ldc.i4.0
0x4c5f  cgt
0x4c61  stsfld   bool Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::traceToConsole
0x4c66  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x4c6b  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x4c70  stsfld   int32 Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::ProcessId
0x4c75  ldc.i4.5
0x4c76  newarr   [mscorlib]System.String
0x4c7b  dup
0x4c7c  ldc.i4.0
0x4c7d  ldstr    aThreadid// "threadId"
0x4c82  stelem.ref
0x4c83  dup
0x4c84  ldc.i4.1
0x4c85  ldstr    aProcessid// "processId"
0x4c8a  stelem.ref
0x4c8b  dup
0x4c8c  ldc.i4.2
0x4c8d  ldstr    aWorkerid// "workerId"
0x4c92  stelem.ref
0x4c93  dup
0x4c94  ldc.i4.3
0x4c95  ldstr    aActivityid// "activityId"
0x4c9a  stelem.ref
0x4c9b  dup
0x4c9c  ldc.i4.4
0x4c9d  ldstr    aOrganizationid// "organizationId"
0x4ca2  stelem.ref
0x4ca3  stsfld   string[] Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::DefaultFieldNames
0x4ca8  ldc.i4.5
0x4ca9  newarr   [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.TableFieldType
0x4cae  dup
0x4caf  ldtoken  valuetype __StaticArrayInitTypeSize=20 <PrivateImplementationDetails>::'9D59D85C2E17CB44E9A4638412BE0991BAC4A687'
0x4cb4  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x4cb9  stsfld   valuetype [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.TableFieldType[] Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::DefaultFieldTypes
0x4cbe  ldstr    aErroreventtabl// "ErrorEventTable"
0x4cc3  ldsfld   bool Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::traceToConsole
0x4cc8  box      [mscorlib]System.Boolean
0x4ccd  newobj   instance void [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.Writer::.ctor(string, modopt([mscorlib]System.Runtime.CompilerServices.IsBoxed) modopt([mscorlib]System.Boolean) class [mscorlib]System.ValueType)
0x4cd2  stsfld   class [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.Writer Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::writer
0x4cd7  ret
```
