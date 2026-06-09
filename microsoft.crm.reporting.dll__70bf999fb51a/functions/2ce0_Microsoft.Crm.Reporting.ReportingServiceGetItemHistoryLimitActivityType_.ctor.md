# Microsoft.Crm.Reporting.ReportingServiceGetItemHistoryLimitActivityType::.ctor

- ea: `0x2ce0`
- end: `0x2cee`
- name: `Microsoft.Crm.Reporting.ReportingServiceGetItemHistoryLimitActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2ce1`: `ReportingService.GetItemHistoryLimit`

## pseudocode

```c

```

## disassembly

```asm
0x2ce0  ldarg.0
0x2ce1  ldstr    aReportingservi_11// "ReportingService.GetItemHistoryLimit"
0x2ce6  ldc.i4.1
0x2ce7  ldc.i4.1
0x2ce8  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceGetItemHistoryLimitActivityType>::.ctor(string, bool, bool)
0x2ced  ret
```
