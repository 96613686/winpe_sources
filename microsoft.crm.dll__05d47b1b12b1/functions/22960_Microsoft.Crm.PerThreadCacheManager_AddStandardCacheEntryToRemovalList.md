# Microsoft.Crm.PerThreadCacheManager::AddStandardCacheEntryToRemovalList

- ea: `0x22960`
- end: `0x229dc`
- name: `Microsoft.Crm.PerThreadCacheManager::AddStandardCacheEntryToRemovalList`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x22740`

## callees

- `0x22960`
- `0x22b20`
- `0x22b80`

## string_xrefs

- `0x229ba`: `Added cache key {0} to removal list in PerThreadCacheManager with CacheIdentifier:PerThreadCacheIdentifier={1}:{2}`

## pseudocode

```c

```

## disassembly

```asm
0x22960  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x22965  stloc.0
0x22966  ldarg.0
0x22967  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>> Microsoft.Crm.PerThreadCacheManager::_cacheEntriesMarkedForRemoval
0x2296c  ldarg.1
0x2296d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>>::ContainsKey(var<u1>)
0x22972  brfalse.s loc_22998
0x22974  ldarg.0
0x22975  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>> Microsoft.Crm.PerThreadCacheManager::_cacheEntriesMarkedForRemoval
0x2297a  ldarg.1
0x2297b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>>::get_Item(void)
0x22980  callvirt instance var<u1> class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>::get_Item2()
0x22985  stloc.0
0x22986  ldloc.0
0x22987  ldarg.2
0x22988  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x2298d  brtrue.s loc_229B2
0x2298f  ldloc.0
0x22990  ldarg.2
0x22991  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x22996  br.s     loc_229B2
0x22998  ldloc.0
0x22999  ldarg.2
0x2299a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2299f  ldarg.0
0x229a0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>> Microsoft.Crm.PerThreadCacheManager::_cacheEntriesMarkedForRemoval
0x229a5  ldarg.1
0x229a6  ldarg.3
0x229a7  ldloc.0
0x229a8  newobj   instance void class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>::.ctor(var<u1>, !!T0)
0x229ad  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>>::Add(var<u1>, !!T0)
0x229b2  ldarg.0
0x229b3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.PerThreadCacheManager::get_OrganizationId()
0x229b8  ldc.i4.s 0x1A
0x229ba  ldstr    aAddedCacheKey0// "Added cache key {0} to removal list in "...
0x229bf  ldc.i4.3
0x229c0  newarr   [mscorlib]System.Object
0x229c5  dup
0x229c6  ldc.i4.0
0x229c7  ldarg.2
0x229c8  stelem.ref
0x229c9  dup
0x229ca  ldc.i4.1
0x229cb  ldarg.1
0x229cc  stelem.ref
0x229cd  dup
0x229ce  ldc.i4.2
0x229cf  ldarg.0
0x229d0  call     instance string Microsoft.Crm.PerThreadCacheManager::get_ThreadLevelCacheIdentifier()
0x229d5  stelem.ref
0x229d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x229db  ret
```
