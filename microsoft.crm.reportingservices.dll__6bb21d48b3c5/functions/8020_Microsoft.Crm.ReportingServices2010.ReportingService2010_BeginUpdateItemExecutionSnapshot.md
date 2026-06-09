# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginUpdateItemExecutionSnapshot

- ea: `0x8020`
- end: `0x8038`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginUpdateItemExecutionSnapshot`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x8021`: `UpdateItemExecutionSnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x8020  ldarg.0
0x8021  ldstr    aUpdateitemexec// "UpdateItemExecutionSnapshot"
0x8026  ldc.i4.1
0x8027  newarr   [mscorlib]System.Object
0x802c  dup
0x802d  ldc.i4.0
0x802e  ldarg.1
0x802f  stelem.ref
0x8030  ldarg.2
0x8031  ldarg.3
0x8032  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x8037  ret
```
