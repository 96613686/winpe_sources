# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginListExtensions

- ea: `0x8f90`
- end: `0x8fa8`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginListExtensions`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x8f91`: `ListExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x8f90  ldarg.0
0x8f91  ldstr    aListextensions// "ListExtensions"
0x8f96  ldc.i4.1
0x8f97  newarr   [mscorlib]System.Object
0x8f9c  dup
0x8f9d  ldc.i4.0
0x8f9e  ldarg.1
0x8f9f  stelem.ref
0x8fa0  ldarg.2
0x8fa1  ldarg.3
0x8fa2  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x8fa7  ret
```
