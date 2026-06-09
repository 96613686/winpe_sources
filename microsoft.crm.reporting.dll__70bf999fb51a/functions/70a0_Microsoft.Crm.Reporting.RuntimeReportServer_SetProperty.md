# Microsoft.Crm.Reporting.RuntimeReportServer::SetProperty

- ea: `0x70a0`
- end: `0x7128`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::SetProperty`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x5e40`

## callees

- `0x2e0`
- `0x4860`
- `0x4970`
- `0x70a0`

## string_xrefs

- `0x70d7`: `Calling ReportingService.SetProperty on: report {0}, property {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x70a0  ldc.i4.1
0x70a1  newarr   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property
0x70a6  stloc.0
0x70a7  ldloc.0
0x70a8  ldc.i4.0
0x70a9  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::.ctor()
0x70ae  stelem.ref
0x70af  ldloc.0
0x70b0  ldc.i4.0
0x70b1  ldelem.ref
0x70b2  ldarg.2
0x70b3  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::set_Name(string)
0x70b8  ldloc.0
0x70b9  ldc.i4.0
0x70ba  ldelem.ref
0x70bb  ldarg.3
0x70bc  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::set_Value(string)
0x70c1  ldarg.0
0x70c2  ldfld    class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext Microsoft.Crm.Reporting.RuntimeReportServer::_organizationContext
0x70c7  ldarg.1
0x70c8  ldarg.s  4
0x70ca  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::GetItemPath(string, bool)
0x70cf  stloc.1
0x70d0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x70d5  ldc.i4.s 0x20
0x70d7  ldstr    aCallingReporti_17// "Calling ReportingService.SetProperty on"...
0x70dc  ldc.i4.2
0x70dd  newarr   [mscorlib]System.Object
0x70e2  dup
0x70e3  ldc.i4.0
0x70e4  ldloc.1
0x70e5  stelem.ref
0x70e6  dup
0x70e7  ldc.i4.1
0x70e8  ldarg.2
0x70e9  stelem.ref
0x70ea  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x70ef  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x70f4  stloc.2
0x70f5  ldarg.0
0x70f6  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x70fb  ldloc.1
0x70fc  ldloc.0
0x70fd  callvirt instance void Microsoft.Crm.Reporting.IReportingService::SetProperties(string ItemPath, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[] Properties)
0x7102  leave.s  loc_7127
0x7104  stloc.3
0x7105  ldarg.s  5
0x7107  brfalse.s loc_710B
0x7109  leave.s  loc_7127
0x710b  ldarg.0
0x710c  ldloc.3
0x710d  ldstr    aSetproperties// "SetProperties"
0x7112  ldc.i4   0x8004832A
0x7117  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x711c  throw
0x711d  ldloc.2
0x711e  brfalse.s loc_7126
0x7120  ldloc.2
0x7121  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7126  endfinally
0x7127  ret
```
