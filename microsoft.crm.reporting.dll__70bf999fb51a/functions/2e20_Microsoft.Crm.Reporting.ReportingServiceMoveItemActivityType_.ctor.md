# Microsoft.Crm.Reporting.ReportingServiceMoveItemActivityType::.ctor

- ea: `0x2e20`
- end: `0x2e2e`
- name: `Microsoft.Crm.Reporting.ReportingServiceMoveItemActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2e21`: `ReportingService.MoveItem`

## pseudocode

```c

```

## disassembly

```asm
0x2e20  ldarg.0
0x2e21  ldstr    aReportingservi_21// "ReportingService.MoveItem"
0x2e26  ldc.i4.1
0x2e27  ldc.i4.1
0x2e28  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceMoveItemActivityType>::.ctor(string, bool, bool)
0x2e2d  ret
```
