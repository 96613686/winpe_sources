# Microsoft.Crm.Reporting.ReportingServiceCreateCatalogItemActivityType::.ctor

- ea: `0x2e00`
- end: `0x2e0e`
- name: `Microsoft.Crm.Reporting.ReportingServiceCreateCatalogItemActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2e01`: `ReportingService.CreateCatalogItem`

## pseudocode

```c

```

## disassembly

```asm
0x2e00  ldarg.0
0x2e01  ldstr    aReportingservi_20// "ReportingService.CreateCatalogItem"
0x2e06  ldc.i4.1
0x2e07  ldc.i4.1
0x2e08  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceCreateCatalogItemActivityType>::.ctor(string, bool, bool)
0x2e0d  ret
```
