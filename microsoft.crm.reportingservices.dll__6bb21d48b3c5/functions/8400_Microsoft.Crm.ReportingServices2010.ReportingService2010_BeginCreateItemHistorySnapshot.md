# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateItemHistorySnapshot

- ea: `0x8400`
- end: `0x8418`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateItemHistorySnapshot`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x8401`: `CreateItemHistorySnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x8400  ldarg.0
0x8401  ldstr    aCreateitemhist// "CreateItemHistorySnapshot"
0x8406  ldc.i4.1
0x8407  newarr   [mscorlib]System.Object
0x840c  dup
0x840d  ldc.i4.0
0x840e  ldarg.1
0x840f  stelem.ref
0x8410  ldarg.2
0x8411  ldarg.3
0x8412  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x8417  ret
```
