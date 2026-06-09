# Microsoft.Crm.Reporting.RuntimeReportServer::GetSnapshots

- ea: `0x5bf0`
- end: `0x5c58`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::GetSnapshots`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x2c0`
- `0x4860`
- `0x4970`
- `0x5bf0`

## string_xrefs

- `0x5c10`: `Calling ReportingService.ListReportHistory on: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x5bf0  ldarg.1
0x5bf1  ldstr    aReportnameonsr_0// "reportNameOnSrs"
0x5bf6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x5bfb  ldarg.0
0x5bfc  ldfld    class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext Microsoft.Crm.Reporting.RuntimeReportServer::_organizationContext
0x5c01  ldarg.1
0x5c02  ldarg.2
0x5c03  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::GetItemPath(string, bool)
0x5c08  stloc.0
0x5c09  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x5c0e  ldc.i4.s 0x20
0x5c10  ldstr    aCallingReporti_6// "Calling ReportingService.ListReportHist"...
0x5c15  ldc.i4.1
0x5c16  newarr   [mscorlib]System.Object
0x5c1b  dup
0x5c1c  ldc.i4.0
0x5c1d  ldloc.0
0x5c1e  stelem.ref
0x5c1f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5c24  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x5c29  stloc.1
0x5c2a  ldarg.0
0x5c2b  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x5c30  ldloc.0
0x5c31  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemHistorySnapshot[] Microsoft.Crm.Reporting.IReportingService::ListItemHistory(string ItemPath)
0x5c36  stloc.2
0x5c37  leave.s  loc_5C56
0x5c39  stloc.3
0x5c3a  ldarg.0
0x5c3b  ldloc.3
0x5c3c  ldstr    aListitemhistor// "ListItemHistory"
0x5c41  ldc.i4   0x8004831F
0x5c46  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x5c4b  throw
0x5c4c  ldloc.1
0x5c4d  brfalse.s loc_5C55
0x5c4f  ldloc.1
0x5c50  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5c55  endfinally
0x5c56  ldloc.2
0x5c57  ret
```
