# Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTelemetryEvent::ALMRollupJobLimitDetectionCompleted

- ea: `0x230`
- end: `0x27a`
- name: `Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTelemetryEvent::ALMRollupJobLimitDetectionCompleted`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x910`

## callees

- `0x230`

## pseudocode

```c

```

## disassembly

```asm
0x230  ldarg.0
0x231  call     instance bool [mscorlib]System.Diagnostics.Tracing.EventSource::IsEnabled()
0x236  brfalse.s loc_279
0x238  ldarg.1
0x239  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::IsTelemetryEnabled(valuetype [mscorlib]System.Guid)
0x23e  brfalse.s loc_279
0x240  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::SetEventSourceActivityId()
0x245  stloc.0
0x246  ldarg.0
0x247  ldc.i4.3
0x248  ldc.i4.4
0x249  newarr   [mscorlib]System.Object
0x24e  dup
0x24f  ldc.i4.0
0x250  ldarg.1
0x251  box      [mscorlib]System.Guid
0x256  stelem.ref
0x257  dup
0x258  ldc.i4.1
0x259  ldarg.2
0x25a  stelem.ref
0x25b  dup
0x25c  ldc.i4.2
0x25d  ldarg.3
0x25e  box      [mscorlib]System.Int32
0x263  stelem.ref
0x264  dup
0x265  ldc.i4.3
0x266  ldarg.s  4
0x268  box      [mscorlib]System.Int32
0x26d  stelem.ref
0x26e  call     instance void [mscorlib]System.Diagnostics.Tracing.EventSource::WriteEvent(int32, object[])
0x273  ldloc.0
0x274  call     void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::ResetEventSourceActivityId(valuetype [mscorlib]System.Guid)
0x279  ret
```
