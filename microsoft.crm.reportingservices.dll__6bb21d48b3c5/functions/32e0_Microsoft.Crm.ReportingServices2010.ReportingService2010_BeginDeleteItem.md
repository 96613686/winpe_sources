# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginDeleteItem

- ea: `0x32e0`
- end: `0x32f8`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginDeleteItem`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x32e1`: `DeleteItem`

## pseudocode

```c

```

## disassembly

```asm
0x32e0  ldarg.0
0x32e1  ldstr    aDeleteitem// "DeleteItem"
0x32e6  ldc.i4.1
0x32e7  newarr   [mscorlib]System.Object
0x32ec  dup
0x32ed  ldc.i4.0
0x32ee  ldarg.1
0x32ef  stelem.ref
0x32f0  ldarg.2
0x32f1  ldarg.3
0x32f2  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x32f7  ret
```
