# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginDeleteCacheRefreshPlan

- ea: `0x9b00`
- end: `0x9b18`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginDeleteCacheRefreshPlan`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x9b01`: `DeleteCacheRefreshPlan`

## pseudocode

```c

```

## disassembly

```asm
0x9b00  ldarg.0
0x9b01  ldstr    aDeletecacheref// "DeleteCacheRefreshPlan"
0x9b06  ldc.i4.1
0x9b07  newarr   [mscorlib]System.Object
0x9b0c  dup
0x9b0d  ldc.i4.0
0x9b0e  ldarg.1
0x9b0f  stelem.ref
0x9b10  ldarg.2
0x9b11  ldarg.3
0x9b12  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x9b17  ret
```
