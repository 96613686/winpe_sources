# Microsoft.Crm.Reporting.ReportingServiceSetItemDataSourcesActivityType::.ctor

- ea: `0x2c00`
- end: `0x2c0e`
- name: `Microsoft.Crm.Reporting.ReportingServiceSetItemDataSourcesActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2c01`: `ReportingService.SetItemDataSources`

## pseudocode

```c

```

## disassembly

```asm
0x2c00  ldarg.0
0x2c01  ldstr    aReportingservi_4// "ReportingService.SetItemDataSources"
0x2c06  ldc.i4.1
0x2c07  ldc.i4.1
0x2c08  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceSetItemDataSourcesActivityType>::.ctor(string, bool, bool)
0x2c0d  ret
```
