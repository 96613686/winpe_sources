# Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2::Put

- ea: `0x1320`
- end: `0x1387`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2::Put`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x12a0`
- `0x1320`

## string_xrefs

- `0x137c`: `InMemoryCache`

## pseudocode

```c

```

## disassembly

```asm
0x1320  newobj   instance void class <>c__DisplayClass5_0<var<u1>, !!T0>::.ctor()
0x1325  stloc.0
0x1326  ldarg.1
0x1327  box      var<u1>
0x132c  brtrue.s loc_1339
0x132e  ldstr    aKey// "key"
0x1333  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1338  throw
0x1339  ldloc.0
0x133a  ldarg.2
0x133b  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::get_UtcNow()
0x1340  newobj   instance void class CachedItem<var<u1>, !!T0>::.ctor(var<u1>, void)
0x1345  stfld    class CachedItem<var<u1>, !!T0> class <>c__DisplayClass5_0<var<u1>, !!T0>::cachedItem
0x134a  ldarg.0
0x134b  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<var<u1>, !!T0> class Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2<var<u1>, !!T0>::dictionary
0x1350  ldarg.1
0x1351  ldloc.0
0x1352  ldfld    class CachedItem<var<u1>, !!T0> class <>c__DisplayClass5_0<var<u1>, !!T0>::cachedItem
0x1357  ldloc.0
0x1358  ldftn    instance class CachedItem<var<u1>, !!T0> class <>c__DisplayClass5_0<var<u1>, !!T0>::<Put>b__0(var<u1>, void)
0x135e  newobj   instance void class [mscorlib]System.Func`3<var<u1>, !!T0, class CachedItem<var<u1>, !!T0>>::.ctor(object, native int)
0x1363  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<var<u1>, !!T0>::AddOrUpdate(void, var<u1>, !!T0)
0x1368  pop
0x1369  ldarg.0
0x136a  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.IInMemoryCacheEvents class Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2<var<u1>, !!T0>::events
0x136f  ldarga.s 1
0x1371  constrained. var<u1>
0x1377  callvirt instance string [mscorlib]System.Object::ToString()
0x137c  ldstr    aInmemorycache// "InMemoryCache"
0x1381  callvirt instance void Microsoft.Xrm.Async.Bridges.FromCommon.IInMemoryCacheEvents::OnCachePut(string key, string callerTypeName)
0x1386  ret
```
