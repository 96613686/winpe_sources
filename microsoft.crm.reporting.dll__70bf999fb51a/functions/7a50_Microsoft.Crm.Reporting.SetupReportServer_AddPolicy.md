# Microsoft.Crm.Reporting.SetupReportServer::AddPolicy

- ea: `0x7a50`
- end: `0x7aeb`
- name: `Microsoft.Crm.Reporting.SetupReportServer::AddPolicy`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x7af0`

## callees

- `0x300`
- `0x4860`
- `0x4960`
- `0x7a50`

## string_xrefs

- `0x7ab7`: `Calling ReportingService.SetPolicies on item: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x7a50  ldarg.2
0x7a51  ldlen
0x7a52  conv.i4
0x7a53  ldc.i4.1
0x7a54  add
0x7a55  newarr   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy
0x7a5a  stloc.0
0x7a5b  ldc.i4.0
0x7a5c  stloc.3
0x7a5d  br.s     loc_7A69
0x7a5f  ldloc.0
0x7a60  ldloc.3
0x7a61  ldarg.2
0x7a62  ldloc.3
0x7a63  ldelem.ref
0x7a64  stelem.ref
0x7a65  ldloc.3
0x7a66  ldc.i4.1
0x7a67  add
0x7a68  stloc.3
0x7a69  ldloc.3
0x7a6a  ldarg.2
0x7a6b  ldlen
0x7a6c  conv.i4
0x7a6d  blt.s    loc_7A5F
0x7a6f  ldc.i4.1
0x7a70  newarr   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Role
0x7a75  stloc.1
0x7a76  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Role::.ctor()
0x7a7b  stloc.2
0x7a7c  ldloc.2
0x7a7d  ldarg.s  4
0x7a7f  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Role::set_Name(string)
0x7a84  ldloc.2
0x7a85  ldarg.s  5
0x7a87  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Role::set_Description(string)
0x7a8c  ldloc.1
0x7a8d  ldc.i4.0
0x7a8e  ldloc.2
0x7a8f  stelem.ref
0x7a90  ldloc.0
0x7a91  ldarg.2
0x7a92  ldlen
0x7a93  conv.i4
0x7a94  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy::.ctor()
0x7a99  stelem.ref
0x7a9a  ldloc.0
0x7a9b  ldarg.2
0x7a9c  ldlen
0x7a9d  conv.i4
0x7a9e  ldelem.ref
0x7a9f  ldarg.3
0x7aa0  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy::set_GroupUserName(string)
0x7aa5  ldloc.0
0x7aa6  ldarg.2
0x7aa7  ldlen
0x7aa8  conv.i4
0x7aa9  ldelem.ref
0x7aaa  ldloc.1
0x7aab  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy::set_Roles(class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Role[])
0x7ab0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x7ab5  ldc.i4.s 0x20
0x7ab7  ldstr    aCallingReporti_22// "Calling ReportingService.SetPolicies on"...
0x7abc  ldc.i4.1
0x7abd  newarr   [mscorlib]System.Object
0x7ac2  dup
0x7ac3  ldc.i4.0
0x7ac4  ldarg.1
0x7ac5  stelem.ref
0x7ac6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7acb  ldarg.0
0x7acc  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x7ad1  ldarg.1
0x7ad2  ldloc.0
0x7ad3  callvirt instance void Microsoft.Crm.Reporting.IReportingService::SetPolicies(string ItemPath, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy[] Policies)
0x7ad8  leave.s  loc_7AEA
0x7ada  stloc.s  4
0x7adc  ldarg.0
0x7add  ldloc.s  4
0x7adf  ldstr    aSetpolicies// "SetPolicies"
0x7ae4  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName)
0x7ae9  throw
0x7aea  ret
```
