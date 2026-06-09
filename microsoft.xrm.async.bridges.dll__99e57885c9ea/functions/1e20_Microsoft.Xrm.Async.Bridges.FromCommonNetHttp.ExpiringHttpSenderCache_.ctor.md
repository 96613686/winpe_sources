# Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ExpiringHttpSenderCache::.ctor

- ea: `0x1e20`
- end: `0x1e35`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ExpiringHttpSenderCache::.ctor`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1e20  ldarg.0
0x1e21  call     instance void [mscorlib]System.Object::.ctor()
0x1e26  ldarg.0
0x1e27  ldarg.1
0x1e28  stfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ICache`2<class [System]System.Uri, class [System.Net.Http]System.Net.Http.HttpMessageInvoker> Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ExpiringHttpSenderCache::cache
0x1e2d  ldarg.0
0x1e2e  ldarg.2
0x1e2f  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.IHttpSenderFactory Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ExpiringHttpSenderCache::innerFactory
0x1e34  ret
```
