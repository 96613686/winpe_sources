# Microsoft.Crm.ReportingServices2010.ReportingService2010::ListExtensionTypes

- ea: `0x9050`
- end: `0x9069`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::ListExtensionTypes`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x9051`: `ListExtensionTypes`

## pseudocode

```c

```

## disassembly

```asm
0x9050  ldarg.0
0x9051  ldstr    aListextensiont// "ListExtensionTypes"
0x9056  ldc.i4.0
0x9057  newarr   [mscorlib]System.Object
0x905c  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x9061  ldc.i4.0
0x9062  ldelem.ref
0x9063  castclass string[]
0x9068  ret
```
