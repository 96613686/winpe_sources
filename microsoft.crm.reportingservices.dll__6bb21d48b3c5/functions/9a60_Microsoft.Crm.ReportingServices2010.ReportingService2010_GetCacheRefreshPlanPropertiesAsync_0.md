# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheRefreshPlanPropertiesAsync_0

- ea: `0x9a60`
- end: `0x9a97`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheRefreshPlanPropertiesAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a50`

## callees

- `0x9a60`

## string_xrefs

- `0x9a7b`: `GetCacheRefreshPlanProperties`

## pseudocode

```c

```

## disassembly

```asm
0x9a60  ldarg.0
0x9a61  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheRefreshPlanPropertiesOperationCompleted
0x9a66  brtrue.s loc_9A7A
0x9a68  ldarg.0
0x9a69  ldarg.0
0x9a6a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetCacheRefreshPlanPropertiesOperationCompleted(object arg)
0x9a70  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x9a75  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheRefreshPlanPropertiesOperationCompleted
0x9a7a  ldarg.0
0x9a7b  ldstr    aGetcacherefres// "GetCacheRefreshPlanProperties"
0x9a80  ldc.i4.1
0x9a81  newarr   [mscorlib]System.Object
0x9a86  dup
0x9a87  ldc.i4.0
0x9a88  ldarg.1
0x9a89  stelem.ref
0x9a8a  ldarg.0
0x9a8b  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheRefreshPlanPropertiesOperationCompleted
0x9a90  ldarg.2
0x9a91  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x9a96  ret
```
