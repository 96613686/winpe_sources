# Microsoft.Crm.ReportingServices.ReportingService::BeginCreateFolder

- ea: `0x11110`
- end: `0x11132`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginCreateFolder`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x11111`: `CreateFolder`

## pseudocode

```c

```

## disassembly

```asm
0x11110  ldarg.0
0x11111  ldstr    aCreatefolder// "CreateFolder"
0x11116  ldc.i4.3
0x11117  newarr   [mscorlib]System.Object
0x1111c  dup
0x1111d  ldc.i4.0
0x1111e  ldarg.1
0x1111f  stelem.ref
0x11120  dup
0x11121  ldc.i4.1
0x11122  ldarg.2
0x11123  stelem.ref
0x11124  dup
0x11125  ldc.i4.2
0x11126  ldarg.3
0x11127  stelem.ref
0x11128  ldarg.s  4
0x1112a  ldarg.s  5
0x1112c  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x11131  ret
```
