# Microsoft.Crm.Reporting.SetupReportServer::RoleExists

- ea: `0x8230`
- end: `0x8292`
- name: `Microsoft.Crm.Reporting.SetupReportServer::RoleExists`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7cc0`
- `0x7dc0`

## callees

- `0x330`
- `0x4860`
- `0x4960`
- `0x8230`

## string_xrefs

- `0x8237`: `Calling ReportingService.ListRoles`

## pseudocode

```c

```

## disassembly

```asm
0x8230  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x8235  ldc.i4.s 0x20
0x8237  ldstr    aCallingReporti_27// "Calling ReportingService.ListRoles"
0x823c  ldc.i4.0
0x823d  newarr   [mscorlib]System.Object
0x8242  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8247  ldarg.0
0x8248  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x824d  ldstr    aCatalog// "Catalog"
0x8252  ldnull
0x8253  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Role[] Microsoft.Crm.Reporting.IReportingService::ListRoles(string SecurityScope, string SiteUrl)
0x8258  stloc.0
0x8259  leave.s  loc_8269
0x825b  stloc.1
0x825c  ldarg.0
0x825d  ldloc.1
0x825e  ldstr    aListroles// "ListRoles"
0x8263  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName)
0x8268  throw
0x8269  ldloc.0
0x826a  stloc.2
0x826b  ldc.i4.0
0x826c  stloc.3
0x826d  br.s     loc_828A
0x826f  ldloc.2
0x8270  ldloc.3
0x8271  ldelem.ref
0x8272  stloc.s  4
0x8274  ldarg.1
0x8275  ldloc.s  4
0x8277  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Role::get_Name()
0x827c  ldc.i4.5
0x827d  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x8282  brfalse.s loc_8286
0x8284  ldc.i4.1
0x8285  ret
0x8286  ldloc.3
0x8287  ldc.i4.1
0x8288  add
0x8289  stloc.3
0x828a  ldloc.3
0x828b  ldloc.2
0x828c  ldlen
0x828d  conv.i4
0x828e  blt.s    loc_826F
0x8290  ldc.i4.0
0x8291  ret
```
