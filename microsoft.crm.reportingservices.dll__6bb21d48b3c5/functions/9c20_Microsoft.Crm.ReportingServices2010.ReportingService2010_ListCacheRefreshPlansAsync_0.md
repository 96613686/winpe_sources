# Microsoft.Crm.ReportingServices2010.ReportingService2010::ListCacheRefreshPlansAsync_0

- ea: `0x9c20`
- end: `0x9c57`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::ListCacheRefreshPlansAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9c10`

## callees

- `0x9c20`

## string_xrefs

- `0x9c3b`: `ListCacheRefreshPlans`

## pseudocode

```c

```

## disassembly

```asm
0x9c20  ldarg.0
0x9c21  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListCacheRefreshPlansOperationCompleted
0x9c26  brtrue.s loc_9C3A
0x9c28  ldarg.0
0x9c29  ldarg.0
0x9c2a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnListCacheRefreshPlansOperationCompleted(object arg)
0x9c30  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x9c35  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListCacheRefreshPlansOperationCompleted
0x9c3a  ldarg.0
0x9c3b  ldstr    aListcacherefre// "ListCacheRefreshPlans"
0x9c40  ldc.i4.1
0x9c41  newarr   [mscorlib]System.Object
0x9c46  dup
0x9c47  ldc.i4.0
0x9c48  ldarg.1
0x9c49  stelem.ref
0x9c4a  ldarg.0
0x9c4b  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListCacheRefreshPlansOperationCompleted
0x9c50  ldarg.2
0x9c51  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x9c56  ret
```
