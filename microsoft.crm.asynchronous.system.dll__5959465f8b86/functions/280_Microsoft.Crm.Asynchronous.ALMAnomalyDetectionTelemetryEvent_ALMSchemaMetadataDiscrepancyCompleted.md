# Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTelemetryEvent::ALMSchemaMetadataDiscrepancyCompleted

- ea: `0x280`
- end: `0x2e8`
- name: `Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTelemetryEvent::ALMSchemaMetadataDiscrepancyCompleted`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6f0`

## callees

- `0x280`

## pseudocode

```c

```

## disassembly

```asm
0x280  ldarg.0
0x281  call     instance bool [mscorlib]System.Diagnostics.Tracing.EventSource::IsEnabled()
0x286  brfalse.s loc_2E7
0x288  ldarg.1
0x289  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::IsTelemetryEnabled(valuetype [mscorlib]System.Guid)
0x28e  brfalse.s loc_2E7
0x290  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::SetEventSourceActivityId()
0x295  stloc.0
0x296  ldarg.0
0x297  ldc.i4.2
0x298  ldc.i4.7
0x299  newarr   [mscorlib]System.Object
0x29e  dup
0x29f  ldc.i4.0
0x2a0  ldarg.1
0x2a1  box      [mscorlib]System.Guid
0x2a6  stelem.ref
0x2a7  dup
0x2a8  ldc.i4.1
0x2a9  ldarg.2
0x2aa  stelem.ref
0x2ab  dup
0x2ac  ldc.i4.2
0x2ad  ldarg.3
0x2ae  box      [mscorlib]System.Int32
0x2b3  stelem.ref
0x2b4  dup
0x2b5  ldc.i4.3
0x2b6  ldarg.s  4
0x2b8  box      [mscorlib]System.Int32
0x2bd  stelem.ref
0x2be  dup
0x2bf  ldc.i4.4
0x2c0  ldarg.s  5
0x2c2  box      [mscorlib]System.Int32
0x2c7  stelem.ref
0x2c8  dup
0x2c9  ldc.i4.5
0x2ca  ldarg.s  6
0x2cc  box      [mscorlib]System.Int32
0x2d1  stelem.ref
0x2d2  dup
0x2d3  ldc.i4.6
0x2d4  ldarg.s  7
0x2d6  box      [mscorlib]System.Int32
0x2db  stelem.ref
0x2dc  call     instance void [mscorlib]System.Diagnostics.Tracing.EventSource::WriteEvent(int32, object[])
0x2e1  ldloc.0
0x2e2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::ResetEventSourceActivityId(valuetype [mscorlib]System.Guid)
0x2e7  ret
```
