# Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2::Expire

- ea: `0x1420`
- end: `0x1475`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2::Expire`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1290`
- `0x1420`

## string_xrefs

- `0x1433`: `InMemoryCache`

## pseudocode

```c

```

## disassembly

```asm
0x1420  ldarg.0
0x1421  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.IInMemoryCacheEvents class Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2<var<u1>, !!T0>::events
0x1426  ldarga.s 1
0x1428  constrained. var<u1>
0x142e  callvirt instance string [mscorlib]System.Object::ToString()
0x1433  ldstr    aInmemorycache// "InMemoryCache"
0x1438  callvirt instance void Microsoft.Xrm.Async.Bridges.FromCommon.IInMemoryCacheEvents::OnCacheExpire(string key, string callerTypeName)
0x143d  ldarg.0
0x143e  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<var<u1>, !!T0> class Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2<var<u1>, !!T0>::dictionary
0x1443  ldarg.1
0x1444  ldloca.s 0
0x1446  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<var<u1>, !!T0>::TryRemove(var<u1>, !!T0)
0x144b  pop
0x144c  ldloc.0
0x144d  brtrue.s loc_145A
0x144f  ldloca.s 1
0x1451  initobj  var<u1>
0x1457  ldloc.1
0x1458  br.s     loc_1460
0x145a  ldloc.0
0x145b  call     instance var<u1> class CachedItem<var<u1>, !!T0>::get_Value()
0x1460  box      var<u1>
0x1465  isinst   [mscorlib]System.IDisposable
0x146a  dup
0x146b  brtrue.s loc_146F
0x146d  pop
0x146e  ret
0x146f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1474  ret
```
