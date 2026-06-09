# Microsoft.Crm.Reporting.ReportingServiceSetItemHistoryLimitActivityType::.ctor

- ea: `0x2e80`
- end: `0x2e8e`
- name: `Microsoft.Crm.Reporting.ReportingServiceSetItemHistoryLimitActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2e81`: `ReportingService.SetItemHistoryLimit`

## pseudocode

```c

```

## disassembly

```asm
0x2e80  ldarg.0
0x2e81  ldstr    aReportingservi_24// "ReportingService.SetItemHistoryLimit"
0x2e86  ldc.i4.1
0x2e87  ldc.i4.1
0x2e88  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceSetItemHistoryLimitActivityType>::.ctor(string, bool, bool)
0x2e8d  ret
```
