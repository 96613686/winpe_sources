# Microsoft.Crm.Tools.Admin.SetupTelemetryEvents::SetupSolutionInstalled

- ea: `0x2880`
- end: `0x292b`
- name: `Microsoft.Crm.Tools.Admin.SetupTelemetryEvents::SetupSolutionInstalled`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2b40`

## callees

- `0x2880`

## string_xrefs

- `0x28ef`: `NOT AN ERROR SetupSolutionInstalled: {0}, {1} {2}, {3}, {4}, {5}, {6}, {7}`

## pseudocode

```c

```

## disassembly

```asm
0x2880  ldarg.0
0x2881  call     instance bool [mscorlib]System.Diagnostics.Tracing.EventSource::IsEnabled()
0x2886  brfalse.s loc_28DE
0x2888  ldarg.1
0x2889  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::IsTelemetryEnabled(valuetype [mscorlib]System.Guid)
0x288e  brfalse.s loc_28DE
0x2890  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::SetEventSourceActivityId()
0x2895  stloc.0
0x2896  ldarg.0
0x2897  ldc.i4.1
0x2898  ldc.i4.s 9
0x289a  newarr   [mscorlib]System.Object
0x289f  dup
0x28a0  ldc.i4.0
0x28a1  ldarg.1
0x28a2  box      [mscorlib]System.Guid
0x28a7  stelem.ref
0x28a8  dup
0x28a9  ldc.i4.1
0x28aa  ldarg.2
0x28ab  stelem.ref
0x28ac  dup
0x28ad  ldc.i4.2
0x28ae  ldarg.3
0x28af  stelem.ref
0x28b0  dup
0x28b1  ldc.i4.3
0x28b2  ldarg.s  4
0x28b4  stelem.ref
0x28b5  dup
0x28b6  ldc.i4.4
0x28b7  ldarg.s  5
0x28b9  stelem.ref
0x28ba  dup
0x28bb  ldc.i4.5
0x28bc  ldarg.s  6
0x28be  stelem.ref
0x28bf  dup
0x28c0  ldc.i4.6
0x28c1  ldarg.s  7
0x28c3  stelem.ref
0x28c4  dup
0x28c5  ldc.i4.7
0x28c6  ldarg.s  8
0x28c8  stelem.ref
0x28c9  dup
0x28ca  ldc.i4.8
0x28cb  ldarg.s  9
0x28cd  box      [mscorlib]System.Int64
0x28d2  stelem.ref
0x28d3  call     instance void [mscorlib]System.Diagnostics.Tracing.EventSource::WriteEvent(int32, object[])
0x28d8  ldloc.0
0x28d9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::ResetEventSourceActivityId(valuetype [mscorlib]System.Guid)
0x28de  ldsfld   int32 Microsoft.Crm.Tools.Admin.SetupTelemetryEvents::IsTelemetryTraceEnabled
0x28e3  ldc.i4.1
0x28e4  bne.un.s loc_292A
0x28e6  ldnull
0x28e7  ldarg.1
0x28e8  ldc.i4.s 0x14
0x28ea  ldc.i4   0x3E7
0x28ef  ldstr    aNotAnErrorSetu// "NOT AN ERROR SetupSolutionInstalled: {0"...
0x28f4  ldc.i4.8
0x28f5  newarr   [mscorlib]System.Object
0x28fa  dup
0x28fb  ldc.i4.0
0x28fc  ldarg.2
0x28fd  stelem.ref
0x28fe  dup
0x28ff  ldc.i4.1
0x2900  ldarg.3
0x2901  stelem.ref
0x2902  dup
0x2903  ldc.i4.2
0x2904  ldarg.s  4
0x2906  stelem.ref
0x2907  dup
0x2908  ldc.i4.3
0x2909  ldarg.s  5
0x290b  stelem.ref
0x290c  dup
0x290d  ldc.i4.4
0x290e  ldarg.s  6
0x2910  stelem.ref
0x2911  dup
0x2912  ldc.i4.5
0x2913  ldarg.s  7
0x2915  stelem.ref
0x2916  dup
0x2917  ldc.i4.6
0x2918  ldarg.s  8
0x291a  stelem.ref
0x291b  dup
0x291c  ldc.i4.7
0x291d  ldarg.s  9
0x291f  box      [mscorlib]System.Int64
0x2924  stelem.ref
0x2925  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x292a  ret
```
