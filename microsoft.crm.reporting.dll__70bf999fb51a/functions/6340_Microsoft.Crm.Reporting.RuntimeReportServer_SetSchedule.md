# Microsoft.Crm.Reporting.RuntimeReportServer::SetSchedule

- ea: `0x6340`
- end: `0x6456`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::SetSchedule`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x360`
- `0x370`
- `0x380`
- `0x4860`
- `0x4970`
- `0x5980`
- `0x6340`
- `0x6900`

## string_xrefs

- `0x637d`: `Calling ReportingService.SetExecutionOptions on: {0}.`
- `0x63bf`: `Calling ReportingService.SetItemHistoryOptions on: {0}.`
- `0x6410`: `Calling ReportingService.SetItemHistoryLimit on: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x6340  ldarg.1
0x6341  ldstr    aReportnameonsr_0// "reportNameOnSrs"
0x6346  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x634b  ldarg.0
0x634c  ldfld    class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext Microsoft.Crm.Reporting.RuntimeReportServer::_organizationContext
0x6351  ldarg.1
0x6352  ldarg.s  4
0x6354  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::GetItemPath(string, bool)
0x6359  stloc.0
0x635a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x635f  stloc.1
0x6360  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.NoSchedule::.ctor()
0x6365  stloc.2
0x6366  ldarg.2
0x6367  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x636c  brtrue.s loc_6376
0x636e  ldarg.2
0x636f  ldarg.3
0x6370  call     class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ScheduleDefinition Microsoft.Crm.Reporting.RuntimeReportServer::DeserializeCrmScheduleDefinition(string scheduleXml, class [mscorlib]System.TimeZone schedulerTimeZone)
0x6375  stloc.2
0x6376  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x637b  ldc.i4.s 0x20
0x637d  ldstr    aCallingReporti_11// "Calling ReportingService.SetExecutionOp"...
0x6382  ldc.i4.1
0x6383  newarr   [mscorlib]System.Object
0x6388  dup
0x6389  ldc.i4.0
0x638a  ldloc.0
0x638b  stelem.ref
0x638c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6391  ldarg.0
0x6392  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x6397  ldloc.0
0x6398  ldstr    aSnapshot// "Snapshot"
0x639d  ldloc.2
0x639e  callvirt instance void Microsoft.Crm.Reporting.IReportingService::SetExecutionOptions(string ItemPath, string ExecutionSetting, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ScheduleDefinitionOrReference Item)
0x63a3  leave.s  loc_63B8
0x63a5  stloc.3
0x63a6  ldarg.0
0x63a7  ldloc.3
0x63a8  ldstr    aSetexecutionop// "SetExecutionOptions"
0x63ad  ldc.i4   0x80048325
0x63b2  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x63b7  throw
0x63b8  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x63bd  ldc.i4.s 0x20
0x63bf  ldstr    aCallingReporti_12// "Calling ReportingService.SetItemHistory"...
0x63c4  ldc.i4.1
0x63c5  newarr   [mscorlib]System.Object
0x63ca  dup
0x63cb  ldc.i4.0
0x63cc  ldloc.0
0x63cd  stelem.ref
0x63ce  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x63d3  ldarg.0
0x63d4  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x63d9  ldloc.0
0x63da  ldc.i4.1
0x63db  ldc.i4.1
0x63dc  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.NoSchedule::.ctor()
0x63e1  callvirt instance void Microsoft.Crm.Reporting.IReportingService::SetItemHistoryOptions(string ItemPath, bool EnableManualSnapshotCreation, bool KeepExecutionSnapshots, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ScheduleDefinitionOrReference Item)
0x63e6  leave.s  loc_63FD
0x63e8  stloc.s  4
0x63ea  ldarg.0
0x63eb  ldloc.s  4
0x63ed  ldstr    aSetitemhistory// "SetItemHistoryOptions"
0x63f2  ldc.i4   0x80048326
0x63f7  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x63fc  throw
0x63fd  ldarg.0
0x63fe  ldarg.1
0x63ff  ldarg.s  4
0x6401  call     instance int32 Microsoft.Crm.Reporting.RuntimeReportServer::GetReportHistoryLimit(string reportNameOnSrs, bool isSharedReport)
0x6406  ldc.i4.0
0x6407  bge.s    loc_6449
0x6409  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x640e  ldc.i4.s 0x20
0x6410  ldstr    aCallingReporti_13// "Calling ReportingService.SetItemHistory"...
0x6415  ldc.i4.1
0x6416  newarr   [mscorlib]System.Object
0x641b  dup
0x641c  ldc.i4.0
0x641d  ldloc.0
0x641e  stelem.ref
0x641f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6424  ldarg.0
0x6425  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x642a  ldloc.0
0x642b  ldc.i4.0
0x642c  ldc.i4.8
0x642d  callvirt instance void Microsoft.Crm.Reporting.IReportingService::SetItemHistoryLimit(string ItemPath, bool UseSystem, int32 HistoryLimit)
0x6432  leave.s  loc_6455
0x6434  stloc.s  5
0x6436  ldarg.0
0x6437  ldloc.s  5
0x6439  ldstr    aSetitemhistory_0// "SetItemHistoryLimit"
0x643e  ldc.i4   0x80048327
0x6443  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x6448  throw
0x6449  leave.s  loc_6455
0x644b  ldloc.1
0x644c  brfalse.s loc_6454
0x644e  ldloc.1
0x644f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6454  endfinally
0x6455  ret
```
