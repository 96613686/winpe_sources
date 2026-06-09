# Microsoft.Crm.Reporting.RuntimeReportServer::GetReportParameters_0

- ea: `0x6d10`
- end: `0x6d65`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::GetReportParameters_0`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x5a00`

## callees

- `0x290`
- `0x4860`
- `0x4970`
- `0x6d10`

## string_xrefs

- `0x6d49`: `GetItemParameters`
- `0x6d17`: `Calling ReportingService.GetParameters on: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x6d10  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x6d15  ldc.i4.s 0x20
0x6d17  ldstr    aCallingReporti_15// "Calling ReportingService.GetParameters "...
0x6d1c  ldc.i4.1
0x6d1d  newarr   [mscorlib]System.Object
0x6d22  dup
0x6d23  ldc.i4.0
0x6d24  ldarg.1
0x6d25  stelem.ref
0x6d26  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6d2b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x6d30  stloc.1
0x6d31  ldarg.0
0x6d32  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x6d37  ldarg.1
0x6d38  ldarg.2
0x6d39  ldarg.3
0x6d3a  ldarg.s  4
0x6d3c  ldarg.s  5
0x6d3e  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter[] Microsoft.Crm.Reporting.IReportingService::GetItemParameters(string ItemPath, string HistoryID, bool ForRendering, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue[] Values, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceCredentials[] Credentials)
0x6d43  stloc.0
0x6d44  leave.s  loc_6D63
0x6d46  stloc.2
0x6d47  ldarg.0
0x6d48  ldloc.2
0x6d49  ldstr    aGetitemparamet// "GetItemParameters"
0x6d4e  ldc.i4   0x80048323
0x6d53  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x6d58  throw
0x6d59  ldloc.1
0x6d5a  brfalse.s loc_6D62
0x6d5c  ldloc.1
0x6d5d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d62  endfinally
0x6d63  ldloc.0
0x6d64  ret
```
