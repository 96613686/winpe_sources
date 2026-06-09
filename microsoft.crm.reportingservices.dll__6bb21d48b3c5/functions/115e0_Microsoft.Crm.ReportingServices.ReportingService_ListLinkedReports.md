# Microsoft.Crm.ReportingServices.ReportingService::ListLinkedReports

- ea: `0x115e0`
- end: `0x115fd`
- name: `Microsoft.Crm.ReportingServices.ReportingService::ListLinkedReports`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x115e1`: `ListLinkedReports`

## pseudocode

```c

```

## disassembly

```asm
0x115e0  ldarg.0
0x115e1  ldstr    aListlinkedrepo// "ListLinkedReports"
0x115e6  ldc.i4.1
0x115e7  newarr   [mscorlib]System.Object
0x115ec  dup
0x115ed  ldc.i4.0
0x115ee  ldarg.1
0x115ef  stelem.ref
0x115f0  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x115f5  ldc.i4.0
0x115f6  ldelem.ref
0x115f7  castclass class Microsoft.Crm.ReportingServices.CatalogItem[]
0x115fc  ret
```
