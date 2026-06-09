# Microsoft.Crm.ReportingServices2010.ReportingService2010::ListCacheRefreshPlans

- ea: `0x9bc0`
- end: `0x9bdd`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::ListCacheRefreshPlans`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x9bc1`: `ListCacheRefreshPlans`

## pseudocode

```c

```

## disassembly

```asm
0x9bc0  ldarg.0
0x9bc1  ldstr    aListcacherefre// "ListCacheRefreshPlans"
0x9bc6  ldc.i4.1
0x9bc7  newarr   [mscorlib]System.Object
0x9bcc  dup
0x9bcd  ldc.i4.0
0x9bce  ldarg.1
0x9bcf  stelem.ref
0x9bd0  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x9bd5  ldc.i4.0
0x9bd6  ldelem.ref
0x9bd7  castclass class Microsoft.Crm.ReportingServices2010.CacheRefreshPlan[]
0x9bdc  ret
```
