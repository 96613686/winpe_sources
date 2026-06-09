# Microsoft.Crm.Reporting.ReportingServiceFindItemsActivityType::.ctor

- ea: `0x2c60`
- end: `0x2c6e`
- name: `Microsoft.Crm.Reporting.ReportingServiceFindItemsActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2c61`: `ReportingService.FindItems`

## pseudocode

```c

```

## disassembly

```asm
0x2c60  ldarg.0
0x2c61  ldstr    aReportingservi_7// "ReportingService.FindItems"
0x2c66  ldc.i4.1
0x2c67  ldc.i4.1
0x2c68  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceFindItemsActivityType>::.ctor(string, bool, bool)
0x2c6d  ret
```
