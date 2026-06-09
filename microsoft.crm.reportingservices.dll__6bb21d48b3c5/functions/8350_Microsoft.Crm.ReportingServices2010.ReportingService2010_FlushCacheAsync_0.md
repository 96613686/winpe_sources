# Microsoft.Crm.ReportingServices2010.ReportingService2010::FlushCacheAsync_0

- ea: `0x8350`
- end: `0x8387`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::FlushCacheAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8340`

## callees

- `0x8350`

## string_xrefs

- `0x836b`: `FlushCache`

## pseudocode

```c

```

## disassembly

```asm
0x8350  ldarg.0
0x8351  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::FlushCacheOperationCompleted
0x8356  brtrue.s loc_836A
0x8358  ldarg.0
0x8359  ldarg.0
0x835a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnFlushCacheOperationCompleted(object arg)
0x8360  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x8365  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::FlushCacheOperationCompleted
0x836a  ldarg.0
0x836b  ldstr    aFlushcache// "FlushCache"
0x8370  ldc.i4.1
0x8371  newarr   [mscorlib]System.Object
0x8376  dup
0x8377  ldc.i4.0
0x8378  ldarg.1
0x8379  stelem.ref
0x837a  ldarg.0
0x837b  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::FlushCacheOperationCompleted
0x8380  ldarg.2
0x8381  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x8386  ret
```
