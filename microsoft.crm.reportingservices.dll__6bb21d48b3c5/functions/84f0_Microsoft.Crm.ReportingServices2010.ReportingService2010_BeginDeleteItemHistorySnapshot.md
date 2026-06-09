# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginDeleteItemHistorySnapshot

- ea: `0x84f0`
- end: `0x850d`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginDeleteItemHistorySnapshot`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x84f1`: `DeleteItemHistorySnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x84f0  ldarg.0
0x84f1  ldstr    aDeleteitemhist// "DeleteItemHistorySnapshot"
0x84f6  ldc.i4.2
0x84f7  newarr   [mscorlib]System.Object
0x84fc  dup
0x84fd  ldc.i4.0
0x84fe  ldarg.1
0x84ff  stelem.ref
0x8500  dup
0x8501  ldc.i4.1
0x8502  ldarg.2
0x8503  stelem.ref
0x8504  ldarg.3
0x8505  ldarg.s  4
0x8507  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x850c  ret
```
