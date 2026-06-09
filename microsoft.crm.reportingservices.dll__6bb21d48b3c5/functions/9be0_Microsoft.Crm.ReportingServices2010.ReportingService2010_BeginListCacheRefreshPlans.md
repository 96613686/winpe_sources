# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginListCacheRefreshPlans

- ea: `0x9be0`
- end: `0x9bf8`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginListCacheRefreshPlans`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x9be1`: `ListCacheRefreshPlans`

## pseudocode

```c

```

## disassembly

```asm
0x9be0  ldarg.0
0x9be1  ldstr    aListcacherefre// "ListCacheRefreshPlans"
0x9be6  ldc.i4.1
0x9be7  newarr   [mscorlib]System.Object
0x9bec  dup
0x9bed  ldc.i4.0
0x9bee  ldarg.1
0x9bef  stelem.ref
0x9bf0  ldarg.2
0x9bf1  ldarg.3
0x9bf2  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x9bf7  ret
```
