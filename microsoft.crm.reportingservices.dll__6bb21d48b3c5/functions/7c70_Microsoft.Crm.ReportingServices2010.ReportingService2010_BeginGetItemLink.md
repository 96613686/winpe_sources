# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetItemLink

- ea: `0x7c70`
- end: `0x7c88`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetItemLink`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x7c71`: `GetItemLink`

## pseudocode

```c

```

## disassembly

```asm
0x7c70  ldarg.0
0x7c71  ldstr    aGetitemlink// "GetItemLink"
0x7c76  ldc.i4.1
0x7c77  newarr   [mscorlib]System.Object
0x7c7c  dup
0x7c7d  ldc.i4.0
0x7c7e  ldarg.1
0x7c7f  stelem.ref
0x7c80  ldarg.2
0x7c81  ldarg.3
0x7c82  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x7c87  ret
```
