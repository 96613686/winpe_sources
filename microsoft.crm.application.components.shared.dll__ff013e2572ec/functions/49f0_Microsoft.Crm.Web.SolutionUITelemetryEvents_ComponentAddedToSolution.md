# Microsoft.Crm.Web.SolutionUITelemetryEvents::ComponentAddedToSolution

- ea: `0x49f0`
- end: `0x4a4e`
- name: `Microsoft.Crm.Web.SolutionUITelemetryEvents::ComponentAddedToSolution`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x49f0`

## pseudocode

```c

```

## disassembly

```asm
0x49f0  ldarg.0
0x49f1  call     instance bool [mscorlib]System.Diagnostics.Tracing.EventSource::IsEnabled()
0x49f6  brfalse.s loc_4A4D
0x49f8  ldarg.1
0x49f9  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::IsTelemetryEnabled(valuetype [mscorlib]System.Guid)
0x49fe  brfalse.s loc_4A4D
0x4a00  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::SetEventSourceActivityId()
0x4a05  stloc.0
0x4a06  ldarg.0
0x4a07  ldc.i4.1
0x4a08  ldc.i4.6
0x4a09  newarr   [mscorlib]System.Object
0x4a0e  dup
0x4a0f  ldc.i4.0
0x4a10  ldarg.1
0x4a11  box      [mscorlib]System.Guid
0x4a16  stelem.ref
0x4a17  dup
0x4a18  ldc.i4.1
0x4a19  ldarg.2
0x4a1a  stelem.ref
0x4a1b  dup
0x4a1c  ldc.i4.2
0x4a1d  ldarg.3
0x4a1e  box      [mscorlib]System.Guid
0x4a23  stelem.ref
0x4a24  dup
0x4a25  ldc.i4.3
0x4a26  ldarg.s  4
0x4a28  box      [mscorlib]System.Int32
0x4a2d  stelem.ref
0x4a2e  dup
0x4a2f  ldc.i4.4
0x4a30  ldarg.s  5
0x4a32  box      [mscorlib]System.Int32
0x4a37  stelem.ref
0x4a38  dup
0x4a39  ldc.i4.5
0x4a3a  ldarg.s  6
0x4a3c  box      [mscorlib]System.Int64
0x4a41  stelem.ref
0x4a42  call     instance void [mscorlib]System.Diagnostics.Tracing.EventSource::WriteEvent(int32, object[])
0x4a47  ldloc.0
0x4a48  call     void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::ResetEventSourceActivityId(valuetype [mscorlib]System.Guid)
0x4a4d  ret
```
