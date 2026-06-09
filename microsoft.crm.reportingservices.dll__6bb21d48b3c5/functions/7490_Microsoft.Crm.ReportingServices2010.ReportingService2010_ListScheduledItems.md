# Microsoft.Crm.ReportingServices2010.ReportingService2010::ListScheduledItems

- ea: `0x7490`
- end: `0x74ad`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::ListScheduledItems`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x7491`: `ListScheduledItems`

## pseudocode

```c

```

## disassembly

```asm
0x7490  ldarg.0
0x7491  ldstr    aListscheduledi// "ListScheduledItems"
0x7496  ldc.i4.1
0x7497  newarr   [mscorlib]System.Object
0x749c  dup
0x749d  ldc.i4.0
0x749e  ldarg.1
0x749f  stelem.ref
0x74a0  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x74a5  ldc.i4.0
0x74a6  ldelem.ref
0x74a7  castclass class Microsoft.Crm.ReportingServices2010.CatalogItem[]
0x74ac  ret
```
