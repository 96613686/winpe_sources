# Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteCacheRefreshPlanAsync_0

- ea: `0x9b40`
- end: `0x9b77`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteCacheRefreshPlanAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9b30`

## callees

- `0x9b40`

## string_xrefs

- `0x9b5b`: `DeleteCacheRefreshPlan`

## pseudocode

```c

```

## disassembly

```asm
0x9b40  ldarg.0
0x9b41  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteCacheRefreshPlanOperationCompleted
0x9b46  brtrue.s loc_9B5A
0x9b48  ldarg.0
0x9b49  ldarg.0
0x9b4a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnDeleteCacheRefreshPlanOperationCompleted(object arg)
0x9b50  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x9b55  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteCacheRefreshPlanOperationCompleted
0x9b5a  ldarg.0
0x9b5b  ldstr    aDeletecacheref// "DeleteCacheRefreshPlan"
0x9b60  ldc.i4.1
0x9b61  newarr   [mscorlib]System.Object
0x9b66  dup
0x9b67  ldc.i4.0
0x9b68  ldarg.1
0x9b69  stelem.ref
0x9b6a  ldarg.0
0x9b6b  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteCacheRefreshPlanOperationCompleted
0x9b70  ldarg.2
0x9b71  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x9b76  ret
```
