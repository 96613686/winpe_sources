# Microsoft.Crm.Reporting.ReportingServiceCreateDataSourceActivityType::.ctor

- ea: `0x2b60`
- end: `0x2b6e`
- name: `Microsoft.Crm.Reporting.ReportingServiceCreateDataSourceActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2b61`: `ReportingService.CreateDataSource`

## pseudocode

```c

```

## disassembly

```asm
0x2b60  ldarg.0
0x2b61  ldstr    aReportingservi// "ReportingService.CreateDataSource"
0x2b66  ldc.i4.1
0x2b67  ldc.i4.1
0x2b68  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceCreateDataSourceActivityType>::.ctor(string, bool, bool)
0x2b6d  ret
```
