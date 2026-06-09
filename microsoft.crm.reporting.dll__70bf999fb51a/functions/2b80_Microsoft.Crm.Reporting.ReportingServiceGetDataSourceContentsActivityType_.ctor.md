# Microsoft.Crm.Reporting.ReportingServiceGetDataSourceContentsActivityType::.ctor

- ea: `0x2b80`
- end: `0x2b8e`
- name: `Microsoft.Crm.Reporting.ReportingServiceGetDataSourceContentsActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2b81`: `ReportingService.GetDataSourceContents`

## pseudocode

```c

```

## disassembly

```asm
0x2b80  ldarg.0
0x2b81  ldstr    aReportingservi_0// "ReportingService.GetDataSourceContents"
0x2b86  ldc.i4.1
0x2b87  ldc.i4.1
0x2b88  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceGetDataSourceContentsActivityType>::.ctor(string, bool, bool)
0x2b8d  ret
```
