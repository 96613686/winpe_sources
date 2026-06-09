# Microsoft.Crm.Sandbox.SandboxSdkListener::CallInfoContainsReportActivityId

- ea: `0x5480`
- end: `0x54b4`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::CallInfoContainsReportActivityId`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x4680`

## callees

- `0x5420`
- `0x5480`

## string_xrefs

- `0x54a3`: `ReportingServicesService`

## pseudocode

```c

```

## disassembly

```asm
0x5480  ldc.i4.0
0x5481  stloc.0
0x5482  ldarg.1
0x5483  brfalse.s loc_54B2
0x5485  ldarg.1
0x5486  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ActivityId()
0x548b  stloc.1
0x548c  ldloca.s 1
0x548e  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x5493  brfalse.s loc_54B2
0x5495  ldarg.2
0x5496  call     bool Microsoft.Crm.Sandbox.SandboxSdkListener::IsReportsOperation(string operation)
0x549b  brfalse.s loc_54B2
0x549d  ldarg.1
0x549e  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ProcessName()
0x54a3  ldstr    aReportingservi// "ReportingServicesService"
0x54a8  ldc.i4.1
0x54a9  call     int32 [mscorlib]System.String::Compare(string, string, bool)
0x54ae  brtrue.s loc_54B2
0x54b0  ldc.i4.1
0x54b1  stloc.0
0x54b2  ldloc.0
0x54b3  ret
```
