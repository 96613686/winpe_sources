# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateLinkedItem

- ea: `0x7a90`
- end: `0x7ab7`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateLinkedItem`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x7a91`: `CreateLinkedItem`

## pseudocode

```c

```

## disassembly

```asm
0x7a90  ldarg.0
0x7a91  ldstr    aCreatelinkedit// "CreateLinkedItem"
0x7a96  ldc.i4.4
0x7a97  newarr   [mscorlib]System.Object
0x7a9c  dup
0x7a9d  ldc.i4.0
0x7a9e  ldarg.1
0x7a9f  stelem.ref
0x7aa0  dup
0x7aa1  ldc.i4.1
0x7aa2  ldarg.2
0x7aa3  stelem.ref
0x7aa4  dup
0x7aa5  ldc.i4.2
0x7aa6  ldarg.3
0x7aa7  stelem.ref
0x7aa8  dup
0x7aa9  ldc.i4.3
0x7aaa  ldarg.s  4
0x7aac  stelem.ref
0x7aad  ldarg.s  5
0x7aaf  ldarg.s  6
0x7ab1  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x7ab6  ret
```
