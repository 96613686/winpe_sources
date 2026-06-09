# Microsoft.Crm.ReportingServices.ReportingService::BeginCreateLinkedReport

- ea: `0x11500`
- end: `0x11527`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginCreateLinkedReport`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x11501`: `CreateLinkedReport`

## pseudocode

```c

```

## disassembly

```asm
0x11500  ldarg.0
0x11501  ldstr    aCreatelinkedre// "CreateLinkedReport"
0x11506  ldc.i4.4
0x11507  newarr   [mscorlib]System.Object
0x1150c  dup
0x1150d  ldc.i4.0
0x1150e  ldarg.1
0x1150f  stelem.ref
0x11510  dup
0x11511  ldc.i4.1
0x11512  ldarg.2
0x11513  stelem.ref
0x11514  dup
0x11515  ldc.i4.2
0x11516  ldarg.3
0x11517  stelem.ref
0x11518  dup
0x11519  ldc.i4.3
0x1151a  ldarg.s  4
0x1151c  stelem.ref
0x1151d  ldarg.s  5
0x1151f  ldarg.s  6
0x11521  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x11526  ret
```
