# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginListExtensionTypes

- ea: `0x9070`
- end: `0x9084`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginListExtensionTypes`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x9071`: `ListExtensionTypes`

## pseudocode

```c

```

## disassembly

```asm
0x9070  ldarg.0
0x9071  ldstr    aListextensiont// "ListExtensionTypes"
0x9076  ldc.i4.0
0x9077  newarr   [mscorlib]System.Object
0x907c  ldarg.1
0x907d  ldarg.2
0x907e  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x9083  ret
```
