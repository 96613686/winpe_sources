# Microsoft.Crm.Reporting.SetupReportServer::AssignRole

- ea: `0x7af0`
- end: `0x7b7e`
- name: `Microsoft.Crm.Reporting.SetupReportServer::AssignRole`
- size: `142`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7710`
- `0x7c20`

## callees

- `0x2f0`
- `0x4860`
- `0x4960`
- `0x7a50`
- `0x7af0`
- `0x82a0`

## string_xrefs

- `0x7af7`: `Calling ReportingService.GetPolicies on folder: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x7af0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x7af5  ldc.i4.s 0x20
0x7af7  ldstr    aCallingReporti_23// "Calling ReportingService.GetPolicies on"...
0x7afc  ldc.i4.1
0x7afd  newarr   [mscorlib]System.Object
0x7b02  dup
0x7b03  ldc.i4.0
0x7b04  ldarg.s  4
0x7b06  stelem.ref
0x7b07  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7b0c  ldarg.0
0x7b0d  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x7b12  ldarg.s  4
0x7b14  ldloca.s 0
0x7b16  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy[] Microsoft.Crm.Reporting.IReportingService::GetPolicies(string ItemPath, [out] bool& InheritParent)
0x7b1b  stloc.1
0x7b1c  leave.s  loc_7B2C
0x7b1e  stloc.2
0x7b1f  ldarg.0
0x7b20  ldloc.2
0x7b21  ldstr    aGetpolicies// "GetPolicies"
0x7b26  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName)
0x7b2b  throw
0x7b2c  ldloc.1
0x7b2d  stloc.3
0x7b2e  ldc.i4.0
0x7b2f  stloc.s  4
0x7b31  br.s     loc_7B4C
0x7b33  ldloc.3
0x7b34  ldloc.s  4
0x7b36  ldelem.ref
0x7b37  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy::get_GroupUserName()
0x7b3c  ldarg.1
0x7b3d  ldc.i4.1
0x7b3e  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x7b43  brfalse.s loc_7B46
0x7b45  ret
0x7b46  ldloc.s  4
0x7b48  ldc.i4.1
0x7b49  add
0x7b4a  stloc.s  4
0x7b4c  ldloc.s  4
0x7b4e  ldloc.3
0x7b4f  ldlen
0x7b50  conv.i4
0x7b51  blt.s    loc_7B33
0x7b53  nop
0x7b54  ldarg.0
0x7b55  ldarg.s  4
0x7b57  ldloc.1
0x7b58  ldarg.1
0x7b59  ldarg.2
0x7b5a  ldarg.3
0x7b5b  call     instance void Microsoft.Crm.Reporting.SetupReportServer::AddPolicy(string itemPath, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy[] originalPolicies, string userGroup, string roleName, string roleDescription)
0x7b60  leave.s  loc_7B7D
0x7b62  pop
0x7b63  ldarg.0
0x7b64  ldarg.s  4
0x7b66  ldloc.1
0x7b67  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy[] Microsoft.Crm.Reporting.SetupReportServer::SanitizePolicies(string itemPath, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy[] originalPolicies)
0x7b6c  stloc.s  5
0x7b6e  ldarg.0
0x7b6f  ldarg.s  4
0x7b71  ldloc.s  5
0x7b73  ldarg.1
0x7b74  ldarg.2
0x7b75  ldarg.3
0x7b76  call     instance void Microsoft.Crm.Reporting.SetupReportServer::AddPolicy(string itemPath, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy[] originalPolicies, string userGroup, string roleName, string roleDescription)
0x7b7b  leave.s  loc_7B7D
0x7b7d  ret
```
