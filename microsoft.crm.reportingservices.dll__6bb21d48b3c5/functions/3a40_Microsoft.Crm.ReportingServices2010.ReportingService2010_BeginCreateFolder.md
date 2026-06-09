# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateFolder

- ea: `0x3a40`
- end: `0x3a62`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateFolder`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x3a41`: `CreateFolder`

## pseudocode

```c

```

## disassembly

```asm
0x3a40  ldarg.0
0x3a41  ldstr    aCreatefolder// "CreateFolder"
0x3a46  ldc.i4.3
0x3a47  newarr   [mscorlib]System.Object
0x3a4c  dup
0x3a4d  ldc.i4.0
0x3a4e  ldarg.1
0x3a4f  stelem.ref
0x3a50  dup
0x3a51  ldc.i4.1
0x3a52  ldarg.2
0x3a53  stelem.ref
0x3a54  dup
0x3a55  ldc.i4.2
0x3a56  ldarg.3
0x3a57  stelem.ref
0x3a58  ldarg.s  4
0x3a5a  ldarg.s  5
0x3a5c  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x3a61  ret
```
