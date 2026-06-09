# Microsoft.Crm.ReportingServices2010.ReportingService2010::SetCacheOptionsAsync_0

- ea: `0x8160`
- end: `0x81a5`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::SetCacheOptionsAsync_0`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8150`

## callees

- `0x8160`

## string_xrefs

- `0x817b`: `SetCacheOptions`

## pseudocode

```c

```

## disassembly

```asm
0x8160  ldarg.0
0x8161  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetCacheOptionsOperationCompleted
0x8166  brtrue.s loc_817A
0x8168  ldarg.0
0x8169  ldarg.0
0x816a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnSetCacheOptionsOperationCompleted(object arg)
0x8170  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x8175  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetCacheOptionsOperationCompleted
0x817a  ldarg.0
0x817b  ldstr    aSetcacheoption// "SetCacheOptions"
0x8180  ldc.i4.3
0x8181  newarr   [mscorlib]System.Object
0x8186  dup
0x8187  ldc.i4.0
0x8188  ldarg.1
0x8189  stelem.ref
0x818a  dup
0x818b  ldc.i4.1
0x818c  ldarg.2
0x818d  box      [mscorlib]System.Boolean
0x8192  stelem.ref
0x8193  dup
0x8194  ldc.i4.2
0x8195  ldarg.3
0x8196  stelem.ref
0x8197  ldarg.0
0x8198  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetCacheOptionsOperationCompleted
0x819d  ldarg.s  4
0x819f  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x81a4  ret
```
