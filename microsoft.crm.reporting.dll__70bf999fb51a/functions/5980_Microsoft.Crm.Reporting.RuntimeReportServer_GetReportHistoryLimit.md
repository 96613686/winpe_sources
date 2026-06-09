# Microsoft.Crm.Reporting.RuntimeReportServer::GetReportHistoryLimit

- ea: `0x5980`
- end: `0x59f3`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::GetReportHistoryLimit`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x6340`

## callees

- `0x2b0`
- `0x4860`
- `0x4970`
- `0x5980`

## string_xrefs

- `0x59a9`: `Calling ReportingService.GetItemHistoryLimit on: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x5980  ldarg.1
0x5981  ldstr    aReportnameonsr_0// "reportNameOnSrs"
0x5986  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x598b  ldarg.1
0x598c  stloc.0
0x598d  ldarg.0
0x598e  ldfld    class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext Microsoft.Crm.Reporting.RuntimeReportServer::_organizationContext
0x5993  ldloc.0
0x5994  ldarg.2
0x5995  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::GetItemPath(string, bool)
0x599a  stloc.1
0x599b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x59a0  stloc.s  5
0x59a2  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x59a7  ldc.i4.s 0x20
0x59a9  ldstr    aCallingReporti_5// "Calling ReportingService.GetItemHistory"...
0x59ae  ldc.i4.1
0x59af  newarr   [mscorlib]System.Object
0x59b4  dup
0x59b5  ldc.i4.0
0x59b6  ldloc.1
0x59b7  stelem.ref
0x59b8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x59bd  ldarg.0
0x59be  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x59c3  ldloc.1
0x59c4  ldloca.s 3
0x59c6  ldloca.s 4
0x59c8  callvirt instance int32 Microsoft.Crm.Reporting.IReportingService::GetItemHistoryLimit(string ItemPath, [out] bool& IsSystem, [out] int32& SystemLimit)
0x59cd  stloc.2
0x59ce  leave.s  loc_59F1
0x59d0  stloc.s  6
0x59d2  ldarg.0
0x59d3  ldloc.s  6
0x59d5  ldstr    aGetitemhistory// "GetItemHistoryLimit"
0x59da  ldc.i4   0x8004831E
0x59df  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x59e4  throw
0x59e5  ldloc.s  5
0x59e7  brfalse.s loc_59F0
0x59e9  ldloc.s  5
0x59eb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x59f0  endfinally
0x59f1  ldloc.2
0x59f2  ret
```
