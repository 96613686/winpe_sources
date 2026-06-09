# Microsoft.Crm.Reporting.ReportingServiceListItemHistoryActivityType::.ctor

- ea: `0x2d00`
- end: `0x2d0e`
- name: `Microsoft.Crm.Reporting.ReportingServiceListItemHistoryActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2d01`: `ReportingService.ListItemHistory`

## pseudocode

```c

```

## disassembly

```asm
0x2d00  ldarg.0
0x2d01  ldstr    aReportingservi_12// "ReportingService.ListItemHistory"
0x2d06  ldc.i4.1
0x2d07  ldc.i4.1
0x2d08  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceListItemHistoryActivityType>::.ctor(string, bool, bool)
0x2d0d  ret
```
