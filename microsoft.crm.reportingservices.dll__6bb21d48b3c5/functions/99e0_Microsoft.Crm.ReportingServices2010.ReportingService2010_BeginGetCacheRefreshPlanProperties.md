# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetCacheRefreshPlanProperties

- ea: `0x99e0`
- end: `0x99f8`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetCacheRefreshPlanProperties`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x99e1`: `GetCacheRefreshPlanProperties`

## pseudocode

```c

```

## disassembly

```asm
0x99e0  ldarg.0
0x99e1  ldstr    aGetcacherefres// "GetCacheRefreshPlanProperties"
0x99e6  ldc.i4.1
0x99e7  newarr   [mscorlib]System.Object
0x99ec  dup
0x99ed  ldc.i4.0
0x99ee  ldarg.1
0x99ef  stelem.ref
0x99f0  ldarg.2
0x99f1  ldarg.3
0x99f2  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x99f7  ret
```
