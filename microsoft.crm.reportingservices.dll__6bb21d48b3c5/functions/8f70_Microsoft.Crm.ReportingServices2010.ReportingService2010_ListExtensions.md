# Microsoft.Crm.ReportingServices2010.ReportingService2010::ListExtensions

- ea: `0x8f70`
- end: `0x8f8d`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::ListExtensions`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x8f71`: `ListExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x8f70  ldarg.0
0x8f71  ldstr    aListextensions// "ListExtensions"
0x8f76  ldc.i4.1
0x8f77  newarr   [mscorlib]System.Object
0x8f7c  dup
0x8f7d  ldc.i4.0
0x8f7e  ldarg.1
0x8f7f  stelem.ref
0x8f80  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x8f85  ldc.i4.0
0x8f86  ldelem.ref
0x8f87  castclass class Microsoft.Crm.ReportingServices2010.Extension[]
0x8f8c  ret
```
