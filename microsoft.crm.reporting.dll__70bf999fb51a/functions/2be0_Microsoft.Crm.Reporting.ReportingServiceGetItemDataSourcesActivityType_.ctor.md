# Microsoft.Crm.Reporting.ReportingServiceGetItemDataSourcesActivityType::.ctor

- ea: `0x2be0`
- end: `0x2bee`
- name: `Microsoft.Crm.Reporting.ReportingServiceGetItemDataSourcesActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2be1`: `ReportingService.GetItemDataSources`

## pseudocode

```c

```

## disassembly

```asm
0x2be0  ldarg.0
0x2be1  ldstr    aReportingservi_3// "ReportingService.GetItemDataSources"
0x2be6  ldc.i4.1
0x2be7  ldc.i4.1
0x2be8  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceGetItemDataSourcesActivityType>::.ctor(string, bool, bool)
0x2bed  ret
```
