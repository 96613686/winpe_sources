# Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTelemetryEvent::ALMAnomalyDetectionTaskCompleted

- ea: `0x2f0`
- end: `0x33a`
- name: `Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTelemetryEvent::ALMAnomalyDetectionTaskCompleted`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3d0`

## callees

- `0x2f0`

## pseudocode

```c

```

## disassembly

```asm
0x2f0  ldarg.0
0x2f1  call     instance bool [mscorlib]System.Diagnostics.Tracing.EventSource::IsEnabled()
0x2f6  brfalse.s loc_339
0x2f8  ldarg.1
0x2f9  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::IsTelemetryEnabled(valuetype [mscorlib]System.Guid)
0x2fe  brfalse.s loc_339
0x300  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::SetEventSourceActivityId()
0x305  stloc.0
0x306  ldarg.0
0x307  ldc.i4.1
0x308  ldc.i4.5
0x309  newarr   [mscorlib]System.Object
0x30e  dup
0x30f  ldc.i4.0
0x310  ldarg.1
0x311  box      [mscorlib]System.Guid
0x316  stelem.ref
0x317  dup
0x318  ldc.i4.1
0x319  ldarg.2
0x31a  stelem.ref
0x31b  dup
0x31c  ldc.i4.2
0x31d  ldarg.3
0x31e  stelem.ref
0x31f  dup
0x320  ldc.i4.3
0x321  ldarg.s  4
0x323  box      [mscorlib]System.Boolean
0x328  stelem.ref
0x329  dup
0x32a  ldc.i4.4
0x32b  ldarg.s  5
0x32d  stelem.ref
0x32e  call     instance void [mscorlib]System.Diagnostics.Tracing.EventSource::WriteEvent(int32, object[])
0x333  ldloc.0
0x334  call     void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::ResetEventSourceActivityId(valuetype [mscorlib]System.Guid)
0x339  ret
```
