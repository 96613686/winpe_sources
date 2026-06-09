# Microsoft.Crm.Reporting.RuntimeReportServer::TakeSnapshot

- ea: `0x6460`
- end: `0x64bb`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::TakeSnapshot`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x390`
- `0x4860`
- `0x4970`
- `0x6460`

## string_xrefs

- `0x647b`: `Calling ReportingService.UpdateItemExecutionSnapshot on: {0}.`
- `0x64a0`: `UpdateItemExecutionSnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x6460  ldarg.0
0x6461  ldfld    class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext Microsoft.Crm.Reporting.RuntimeReportServer::_organizationContext
0x6466  ldarg.1
0x6467  ldarg.2
0x6468  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::GetItemPath(string, bool)
0x646d  stloc.0
0x646e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x6473  stloc.1
0x6474  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x6479  ldc.i4.s 0x20
0x647b  ldstr    aCallingReporti_14// "Calling ReportingService.UpdateItemExec"...
0x6480  ldc.i4.1
0x6481  newarr   [mscorlib]System.Object
0x6486  dup
0x6487  ldc.i4.0
0x6488  ldloc.0
0x6489  stelem.ref
0x648a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x648f  ldarg.0
0x6490  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x6495  ldloc.0
0x6496  callvirt instance void Microsoft.Crm.Reporting.IReportingService::UpdateItemExecutionSnapshot(string ItemPath)
0x649b  leave.s  loc_64BA
0x649d  stloc.2
0x649e  ldarg.0
0x649f  ldloc.2
0x64a0  ldstr    aUpdateitemexec// "UpdateItemExecutionSnapshot"
0x64a5  ldc.i4   0x80048328
0x64aa  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x64af  throw
0x64b0  ldloc.1
0x64b1  brfalse.s loc_64B9
0x64b3  ldloc.1
0x64b4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64b9  endfinally
0x64ba  ret
```
