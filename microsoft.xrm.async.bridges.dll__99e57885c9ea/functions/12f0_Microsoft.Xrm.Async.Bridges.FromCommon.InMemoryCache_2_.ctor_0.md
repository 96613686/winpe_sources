# Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2::.ctor_0

- ea: `0x12f0`
- end: `0x1311`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2::.ctor_0`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x12f0  ldarg.0
0x12f1  call     instance void [mscorlib]System.Object::.ctor()
0x12f6  ldarg.0
0x12f7  ldarg.1
0x12f8  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<var<u1>, !!T0>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x12fd  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<var<u1>, !!T0> class Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2<var<u1>, !!T0>::dictionary
0x1302  ldarg.0
0x1303  ldarg.2
0x1304  stfld    valuetype [mscorlib]System.TimeSpan class Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2<var<u1>, !!T0>::timeToLive
0x1309  ldarg.0
0x130a  ldarg.3
0x130b  stfld    class Microsoft.Xrm.Async.Bridges.FromCommon.IInMemoryCacheEvents class Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2<var<u1>, !!T0>::events
0x1310  ret
```
