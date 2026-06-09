# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheOptionsAsync_0

- ea: `0x8270`
- end: `0x82a7`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheOptionsAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8260`

## callees

- `0x8270`

## string_xrefs

- `0x828b`: `GetCacheOptions`

## pseudocode

```c

```

## disassembly

```asm
0x8270  ldarg.0
0x8271  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheOptionsOperationCompleted
0x8276  brtrue.s loc_828A
0x8278  ldarg.0
0x8279  ldarg.0
0x827a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetCacheOptionsOperationCompleted(object arg)
0x8280  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x8285  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheOptionsOperationCompleted
0x828a  ldarg.0
0x828b  ldstr    aGetcacheoption// "GetCacheOptions"
0x8290  ldc.i4.1
0x8291  newarr   [mscorlib]System.Object
0x8296  dup
0x8297  ldc.i4.0
0x8298  ldarg.1
0x8299  stelem.ref
0x829a  ldarg.0
0x829b  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheOptionsOperationCompleted
0x82a0  ldarg.2
0x82a1  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x82a6  ret
```
