# Microsoft.Crm.Asynchronous.ALMAnomalyDetectionJob::Run

- ea: `0x3d0`
- end: `0x4a7`
- name: `Microsoft.Crm.Asynchronous.ALMAnomalyDetectionJob::Run`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180`

## callees

- `0x220`
- `0x2f0`
- `0x3d0`
- `0x630`
- `0x650`
- `0x670`
- `0x890`
- `0x8c0`

## string_xrefs

- `0x422`: `ALM Anomaly Detection task {0} executed for org {1} with status {2} and runmessage {3}`

## pseudocode

```c

```

## disassembly

```asm
0x3d0  ldarg.0
0x3d1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionJob::_organizationId
0x3d6  ldc.i4.s 0x15
0x3d8  ldstr    aAlmAnomalyDete// "ALM Anomaly Detection Job started runni"...
0x3dd  ldc.i4.1
0x3de  newarr   [mscorlib]System.Object
0x3e3  dup
0x3e4  ldc.i4.0
0x3e5  ldarg.0
0x3e6  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionJob::_organizationId
0x3eb  box      [mscorlib]System.Guid
0x3f0  stelem.ref
0x3f1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3f6  ldarg.0
0x3f7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.IALMAnomalyDetectionTask> Microsoft.Crm.Asynchronous.ALMAnomalyDetectionJob::_taskList
0x3fc  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.IALMAnomalyDetectionTask>::GetEnumerator()
0x401  stloc.0
0x402  br       loc_48A
0x407  ldloca.s 0
0x409  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.IALMAnomalyDetectionTask>::get_Current()
0x40e  dup
0x40f  callvirt instance void Microsoft.Crm.Asynchronous.IALMAnomalyDetectionTask::Run()
0x414  callvirt instance class Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus Microsoft.Crm.Asynchronous.IALMAnomalyDetectionTask::ReportTaskStatus()
0x419  stloc.1
0x41a  ldarg.0
0x41b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionJob::_organizationId
0x420  ldc.i4.s 0x15
0x422  ldstr    aAlmAnomalyDete_0// "ALM Anomaly Detection task {0} executed"...
0x427  ldc.i4.4
0x428  newarr   [mscorlib]System.Object
0x42d  dup
0x42e  ldc.i4.0
0x42f  ldloc.1
0x430  callvirt instance string Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus::get_taskName()
0x435  stelem.ref
0x436  dup
0x437  ldc.i4.1
0x438  ldarg.0
0x439  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionJob::_organizationId
0x43e  box      [mscorlib]System.Guid
0x443  stelem.ref
0x444  dup
0x445  ldc.i4.2
0x446  ldloc.1
0x447  callvirt instance valuetype Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatusType Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus::get_taskRunStatusType()
0x44c  box      Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatusType
0x451  stelem.ref
0x452  dup
0x453  ldc.i4.3
0x454  ldloc.1
0x455  callvirt instance string Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus::get_taskRunMessage()
0x45a  stelem.ref
0x45b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x460  call     class Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTelemetryEvent Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTelemetryEvent::get_Instance()
0x465  ldarg.0
0x466  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionJob::_organizationId
0x46b  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x470  ldloc.1
0x471  callvirt instance string Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus::get_taskName()
0x476  ldloc.1
0x477  callvirt instance valuetype Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatusType Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus::get_taskRunStatusType()
0x47c  ldc.i4.4
0x47d  ceq
0x47f  ldloc.1
0x480  callvirt instance string Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus::get_taskRunMessage()
0x485  callvirt instance void Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTelemetryEvent::ALMAnomalyDetectionTaskCompleted(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string taskName, bool hasTaskCompleted, string taskRunMessage)
0x48a  ldloca.s 0
0x48c  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.IALMAnomalyDetectionTask>::MoveNext()
0x491  brtrue   loc_407
0x496  leave.s  loc_4A6
0x498  ldloca.s 0
0x49a  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.IALMAnomalyDetectionTask>
0x4a0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a5  endfinally
0x4a6  ret
```
