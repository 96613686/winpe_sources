# Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2::TryGet

- ea: `0x1390`
- end: `0x1418`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2::TryGet`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x12b0`
- `0x12c0`
- `0x1390`

## string_xrefs

- `0x13b3`: `InMemoryCache`
- `0x1405`: `InMemoryCache`

## pseudocode

```c

```

## disassembly

```asm
0x1390  ldarg.0
0x1391  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<var<u1>, !!T0> class Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2<var<u1>, !!T0>::dictionary
0x1396  ldarg.1
0x1397  ldloca.s 0
0x1399  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<var<u1>, !!T0>::TryGetValue(var<u1>, !!T0)
0x139e  brfalse.s loc_13F2
0x13a0  ldarg.0
0x13a1  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.IInMemoryCacheEvents class Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2<var<u1>, !!T0>::events
0x13a6  ldarga.s 1
0x13a8  constrained. var<u1>
0x13ae  callvirt instance string [mscorlib]System.Object::ToString()
0x13b3  ldstr    aInmemorycache// "InMemoryCache"
0x13b8  callvirt instance void Microsoft.Xrm.Async.Bridges.FromCommon.IInMemoryCacheEvents::OnCacheHit(string key, string callerTypeName)
0x13bd  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::get_UtcNow()
0x13c2  stloc.1
0x13c3  ldloca.s 1
0x13c5  ldloc.0
0x13c6  callvirt instance valuetype [mscorlib]System.DateTimeOffset class CachedItem<var<u1>, !!T0>::get_CachedAt()
0x13cb  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTimeOffset::Subtract(valuetype [mscorlib]System.DateTimeOffset)
0x13d0  ldarg.0
0x13d1  ldfld    valuetype [mscorlib]System.TimeSpan class Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2<var<u1>, !!T0>::timeToLive
0x13d6  call     bool [mscorlib]System.TimeSpan::op_LessThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x13db  brfalse.s loc_13EB
0x13dd  ldarg.2
0x13de  ldloc.0
0x13df  callvirt instance var<u1> class CachedItem<var<u1>, !!T0>::get_Value()
0x13e4  stobj    var<u1>
0x13e9  ldc.i4.1
0x13ea  ret
0x13eb  ldarg.0
0x13ec  ldarg.1
0x13ed  call     instance void class Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2<var<u1>, !!T0>::Expire(var<u1>)
0x13f2  ldarg.0
0x13f3  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.IInMemoryCacheEvents class Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2<var<u1>, !!T0>::events
0x13f8  ldarga.s 1
0x13fa  constrained. var<u1>
0x1400  callvirt instance string [mscorlib]System.Object::ToString()
0x1405  ldstr    aInmemorycache// "InMemoryCache"
0x140a  callvirt instance void Microsoft.Xrm.Async.Bridges.FromCommon.IInMemoryCacheEvents::OnCacheMiss(string key, string callerTypeName)
0x140f  ldarg.2
0x1410  initobj  var<u1>
0x1416  ldc.i4.0
0x1417  ret
```
