# Microsoft.Crm.ReportingServices2010.ReportingService2010::SetCacheRefreshPlanPropertiesAsync_0

- ea: `0x98f0`
- end: `0x993a`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::SetCacheRefreshPlanPropertiesAsync_0`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x98e0`

## callees

- `0x98f0`

## string_xrefs

- `0x990b`: `SetCacheRefreshPlanProperties`

## pseudocode

```c

```

## disassembly

```asm
0x98f0  ldarg.0
0x98f1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetCacheRefreshPlanPropertiesOperationCompleted
0x98f6  brtrue.s loc_990A
0x98f8  ldarg.0
0x98f9  ldarg.0
0x98fa  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnSetCacheRefreshPlanPropertiesOperationCompleted(object arg)
0x9900  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x9905  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetCacheRefreshPlanPropertiesOperationCompleted
0x990a  ldarg.0
0x990b  ldstr    aSetcacherefres// "SetCacheRefreshPlanProperties"
0x9910  ldc.i4.5
0x9911  newarr   [mscorlib]System.Object
0x9916  dup
0x9917  ldc.i4.0
0x9918  ldarg.1
0x9919  stelem.ref
0x991a  dup
0x991b  ldc.i4.1
0x991c  ldarg.2
0x991d  stelem.ref
0x991e  dup
0x991f  ldc.i4.2
0x9920  ldarg.3
0x9921  stelem.ref
0x9922  dup
0x9923  ldc.i4.3
0x9924  ldarg.s  4
0x9926  stelem.ref
0x9927  dup
0x9928  ldc.i4.4
0x9929  ldarg.s  5
0x992b  stelem.ref
0x992c  ldarg.0
0x992d  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetCacheRefreshPlanPropertiesOperationCompleted
0x9932  ldarg.s  6
0x9934  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x9939  ret
```
