# Microsoft.Crm.ReportingServices.ReportingService::BeginListExtensions

- ea: `0x12b20`
- end: `0x12b3d`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginListExtensions`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x12b21`: `ListExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x12b20  ldarg.0
0x12b21  ldstr    aListextensions// "ListExtensions"
0x12b26  ldc.i4.1
0x12b27  newarr   [mscorlib]System.Object
0x12b2c  dup
0x12b2d  ldc.i4.0
0x12b2e  ldarg.1
0x12b2f  box      Microsoft.Crm.ReportingServices.ExtensionTypeEnum
0x12b34  stelem.ref
0x12b35  ldarg.2
0x12b36  ldarg.3
0x12b37  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x12b3c  ret
```
