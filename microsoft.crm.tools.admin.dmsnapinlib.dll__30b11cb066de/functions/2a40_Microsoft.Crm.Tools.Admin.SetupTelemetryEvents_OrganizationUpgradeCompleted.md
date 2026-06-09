# Microsoft.Crm.Tools.Admin.SetupTelemetryEvents::OrganizationUpgradeCompleted

- ea: `0x2a40`
- end: `0x2ae0`
- name: `Microsoft.Crm.Tools.Admin.SetupTelemetryEvents::OrganizationUpgradeCompleted`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2b90`

## callees

- `0x2a40`

## string_xrefs

- `0x2aa9`: `NOT AN ERROR OrganizationUpgradeCompleted: {0}, {1} {2}, {3}, {4}, {5}`

## pseudocode

```c

```

## disassembly

```asm
0x2a40  ldarg.0
0x2a41  call     instance bool [mscorlib]System.Diagnostics.Tracing.EventSource::IsEnabled()
0x2a46  brfalse.s loc_2A98
0x2a48  ldarg.1
0x2a49  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::IsTelemetryEnabled(valuetype [mscorlib]System.Guid)
0x2a4e  brfalse.s loc_2A98
0x2a50  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::SetEventSourceActivityId()
0x2a55  stloc.0
0x2a56  ldarg.0
0x2a57  ldc.i4.3
0x2a58  ldc.i4.7
0x2a59  newarr   [mscorlib]System.Object
0x2a5e  dup
0x2a5f  ldc.i4.0
0x2a60  ldarg.1
0x2a61  box      [mscorlib]System.Guid
0x2a66  stelem.ref
0x2a67  dup
0x2a68  ldc.i4.1
0x2a69  ldarg.2
0x2a6a  stelem.ref
0x2a6b  dup
0x2a6c  ldc.i4.2
0x2a6d  ldarg.3
0x2a6e  stelem.ref
0x2a6f  dup
0x2a70  ldc.i4.3
0x2a71  ldarg.s  4
0x2a73  box      [mscorlib]System.Boolean
0x2a78  stelem.ref
0x2a79  dup
0x2a7a  ldc.i4.4
0x2a7b  ldarg.s  5
0x2a7d  stelem.ref
0x2a7e  dup
0x2a7f  ldc.i4.5
0x2a80  ldarg.s  6
0x2a82  stelem.ref
0x2a83  dup
0x2a84  ldc.i4.6
0x2a85  ldarg.s  7
0x2a87  box      [mscorlib]System.Int64
0x2a8c  stelem.ref
0x2a8d  call     instance void [mscorlib]System.Diagnostics.Tracing.EventSource::WriteEvent(int32, object[])
0x2a92  ldloc.0
0x2a93  call     void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::ResetEventSourceActivityId(valuetype [mscorlib]System.Guid)
0x2a98  ldsfld   int32 Microsoft.Crm.Tools.Admin.SetupTelemetryEvents::IsTelemetryTraceEnabled
0x2a9d  ldc.i4.1
0x2a9e  bne.un.s loc_2ADF
0x2aa0  ldnull
0x2aa1  ldarg.1
0x2aa2  ldc.i4.s 0x14
0x2aa4  ldc.i4   0x3E7
0x2aa9  ldstr    aNotAnErrorOrga// "NOT AN ERROR OrganizationUpgradeComplet"...
0x2aae  ldc.i4.6
0x2aaf  newarr   [mscorlib]System.Object
0x2ab4  dup
0x2ab5  ldc.i4.0
0x2ab6  ldarg.2
0x2ab7  stelem.ref
0x2ab8  dup
0x2ab9  ldc.i4.1
0x2aba  ldarg.3
0x2abb  stelem.ref
0x2abc  dup
0x2abd  ldc.i4.2
0x2abe  ldarg.s  4
0x2ac0  box      [mscorlib]System.Boolean
0x2ac5  stelem.ref
0x2ac6  dup
0x2ac7  ldc.i4.3
0x2ac8  ldarg.s  5
0x2aca  stelem.ref
0x2acb  dup
0x2acc  ldc.i4.4
0x2acd  ldarg.s  6
0x2acf  stelem.ref
0x2ad0  dup
0x2ad1  ldc.i4.5
0x2ad2  ldarg.s  7
0x2ad4  box      [mscorlib]System.Int64
0x2ad9  stelem.ref
0x2ada  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x2adf  ret
```
