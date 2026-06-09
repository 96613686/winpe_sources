# Microsoft.Crm.Tools.Admin.SetupTelemetryEvents::AppliedOrganizationDBUpdate

- ea: `0x2930`
- end: `0x2a39`
- name: `Microsoft.Crm.Tools.Admin.SetupTelemetryEvents::AppliedOrganizationDBUpdate`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2b60`

## callees

- `0x2930`

## string_xrefs

- `0x29d7`: `NOT AN ERROR AppliedOrganizationDBUpdate: {0}, {1} {2}, {3}, {4}, {5}, {6}, {7}, {8}, {9}, {10}`

## pseudocode

```c

```

## disassembly

```asm
0x2930  ldarg.0
0x2931  call     instance bool [mscorlib]System.Diagnostics.Tracing.EventSource::IsEnabled()
0x2936  brfalse  loc_29C6
0x293b  ldarg.1
0x293c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::IsTelemetryEnabled(valuetype [mscorlib]System.Guid)
0x2941  brfalse  loc_29C6
0x2946  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::SetEventSourceActivityId()
0x294b  stloc.0
0x294c  ldarg.0
0x294d  ldc.i4.2
0x294e  ldc.i4.s 0xC
0x2950  newarr   [mscorlib]System.Object
0x2955  dup
0x2956  ldc.i4.0
0x2957  ldarg.1
0x2958  box      [mscorlib]System.Guid
0x295d  stelem.ref
0x295e  dup
0x295f  ldc.i4.1
0x2960  ldarg.2
0x2961  stelem.ref
0x2962  dup
0x2963  ldc.i4.2
0x2964  ldarg.3
0x2965  stelem.ref
0x2966  dup
0x2967  ldc.i4.3
0x2968  ldarg.s  4
0x296a  stelem.ref
0x296b  dup
0x296c  ldc.i4.4
0x296d  ldarg.s  5
0x296f  stelem.ref
0x2970  dup
0x2971  ldc.i4.5
0x2972  ldarg.s  6
0x2974  box      [mscorlib]System.Boolean
0x2979  stelem.ref
0x297a  dup
0x297b  ldc.i4.6
0x297c  ldarg.s  7
0x297e  stelem.ref
0x297f  dup
0x2980  ldc.i4.7
0x2981  ldarg.s  8
0x2983  stelem.ref
0x2984  dup
0x2985  ldc.i4.8
0x2986  ldarg.s  9
0x2988  box      [mscorlib]System.Int64
0x298d  stelem.ref
0x298e  dup
0x298f  ldc.i4.s 9
0x2991  ldarg.s  0xA
0x2993  box      [mscorlib]System.Boolean
0x2998  stelem.ref
0x2999  dup
0x299a  ldc.i4.s 0xA
0x299c  ldarga.s 0xB
0x299e  constrained. Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateMode
0x29a4  callvirt instance string [mscorlib]System.Object::ToString()
0x29a9  stelem.ref
0x29aa  dup
0x29ab  ldc.i4.s 0xB
0x29ad  ldarga.s 0xC
0x29af  constrained. Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateSource
0x29b5  callvirt instance string [mscorlib]System.Object::ToString()
0x29ba  stelem.ref
0x29bb  call     instance void [mscorlib]System.Diagnostics.Tracing.EventSource::WriteEvent(int32, object[])
0x29c0  ldloc.0
0x29c1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::ResetEventSourceActivityId(valuetype [mscorlib]System.Guid)
0x29c6  ldsfld   int32 Microsoft.Crm.Tools.Admin.SetupTelemetryEvents::IsTelemetryTraceEnabled
0x29cb  ldc.i4.1
0x29cc  bne.un.s loc_2A38
0x29ce  ldnull
0x29cf  ldarg.1
0x29d0  ldc.i4.s 0x14
0x29d2  ldc.i4   0x3E7
0x29d7  ldstr    aNotAnErrorAppl// "NOT AN ERROR AppliedOrganizationDBUpdat"...
0x29dc  ldc.i4.s 0xB
0x29de  newarr   [mscorlib]System.Object
0x29e3  dup
0x29e4  ldc.i4.0
0x29e5  ldarg.2
0x29e6  stelem.ref
0x29e7  dup
0x29e8  ldc.i4.1
0x29e9  ldarg.3
0x29ea  stelem.ref
0x29eb  dup
0x29ec  ldc.i4.2
0x29ed  ldarg.s  4
0x29ef  stelem.ref
0x29f0  dup
0x29f1  ldc.i4.3
0x29f2  ldarg.s  5
0x29f4  stelem.ref
0x29f5  dup
0x29f6  ldc.i4.4
0x29f7  ldarg.s  6
0x29f9  box      [mscorlib]System.Boolean
0x29fe  stelem.ref
0x29ff  dup
0x2a00  ldc.i4.5
0x2a01  ldarg.s  7
0x2a03  stelem.ref
0x2a04  dup
0x2a05  ldc.i4.6
0x2a06  ldarg.s  8
0x2a08  stelem.ref
0x2a09  dup
0x2a0a  ldc.i4.7
0x2a0b  ldarg.s  9
0x2a0d  box      [mscorlib]System.Int64
0x2a12  stelem.ref
0x2a13  dup
0x2a14  ldc.i4.8
0x2a15  ldarg.s  0xA
0x2a17  box      [mscorlib]System.Boolean
0x2a1c  stelem.ref
0x2a1d  dup
0x2a1e  ldc.i4.s 9
0x2a20  ldarg.s  0xB
0x2a22  box      Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateMode
0x2a27  stelem.ref
0x2a28  dup
0x2a29  ldc.i4.s 0xA
0x2a2b  ldarg.s  0xC
0x2a2d  box      Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateSource
0x2a32  stelem.ref
0x2a33  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x2a38  ret
```
