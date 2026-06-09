# Microsoft.Crm.ReportingServices.ReportingService::BeginDeleteItem

- ea: `0x10f00`
- end: `0x10f18`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginDeleteItem`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x10f01`: `DeleteItem`

## pseudocode

```c

```

## disassembly

```asm
0x10f00  ldarg.0
0x10f01  ldstr    aDeleteitem// "DeleteItem"
0x10f06  ldc.i4.1
0x10f07  newarr   [mscorlib]System.Object
0x10f0c  dup
0x10f0d  ldc.i4.0
0x10f0e  ldarg.1
0x10f0f  stelem.ref
0x10f10  ldarg.2
0x10f11  ldarg.3
0x10f12  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x10f17  ret
```
