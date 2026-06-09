# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCacheRefreshPlanAsync_0

- ea: `0x97e0`
- end: `0x982a`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCacheRefreshPlanAsync_0`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x97d0`

## callees

- `0x97e0`

## string_xrefs

- `0x97fb`: `CreateCacheRefreshPlan`

## pseudocode

```c

```

## disassembly

```asm
0x97e0  ldarg.0
0x97e1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCacheRefreshPlanOperationCompleted
0x97e6  brtrue.s loc_97FA
0x97e8  ldarg.0
0x97e9  ldarg.0
0x97ea  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateCacheRefreshPlanOperationCompleted(object arg)
0x97f0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x97f5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCacheRefreshPlanOperationCompleted
0x97fa  ldarg.0
0x97fb  ldstr    aCreatecacheref// "CreateCacheRefreshPlan"
0x9800  ldc.i4.5
0x9801  newarr   [mscorlib]System.Object
0x9806  dup
0x9807  ldc.i4.0
0x9808  ldarg.1
0x9809  stelem.ref
0x980a  dup
0x980b  ldc.i4.1
0x980c  ldarg.2
0x980d  stelem.ref
0x980e  dup
0x980f  ldc.i4.2
0x9810  ldarg.3
0x9811  stelem.ref
0x9812  dup
0x9813  ldc.i4.3
0x9814  ldarg.s  4
0x9816  stelem.ref
0x9817  dup
0x9818  ldc.i4.4
0x9819  ldarg.s  5
0x981b  stelem.ref
0x981c  ldarg.0
0x981d  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCacheRefreshPlanOperationCompleted
0x9822  ldarg.s  6
0x9824  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x9829  ret
```
