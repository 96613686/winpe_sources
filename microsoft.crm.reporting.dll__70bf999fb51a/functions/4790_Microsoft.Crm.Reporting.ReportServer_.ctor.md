# Microsoft.Crm.Reporting.ReportServer::.ctor

- ea: `0x4790`
- end: `0x47cf`
- name: `Microsoft.Crm.Reporting.ReportServer::.ctor`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x55e0`
- `0x7550`

## callees

- `0x2ee0`
- `0x4790`

## string_xrefs

- `0x47b3`: `Unable to contact SQL Server Reporting Services server. {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4790  ldarg.0
0x4791  ldc.i4.1
0x4792  stfld    bool Microsoft.Crm.Reporting.ReportServer::_logErrorsToEventLog
0x4797  ldarg.0
0x4798  call     instance void [mscorlib]System.Object::.ctor()
0x479d  ldarg.0
0x479e  ldarg.1
0x479f  newobj   instance void Microsoft.Crm.Reporting.ReportingServiceProxy::.ctor(class [System]System.Uri reportServerUrl)
0x47a4  stfld    class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::_rs
0x47a9  leave.s  loc_47CE
0x47ab  stloc.0
0x47ac  ldloc.0
0x47ad  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x47b2  ldc.i4.0
0x47b3  ldstr    aUnableToContac// "Unable to contact SQL Server Reporting "...
0x47b8  ldc.i4.1
0x47b9  newarr   [mscorlib]System.Object
0x47be  dup
0x47bf  ldc.i4.0
0x47c0  ldloc.0
0x47c1  callvirt instance string [mscorlib]System.Exception::get_Message()
0x47c6  stelem.ref
0x47c7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x47cc  rethrow
0x47ce  ret
```
