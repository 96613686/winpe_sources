# Microsoft.Crm.LocatorCache::AddEntryNoLock

- ea: `0x36b0`
- end: `0x373d`
- name: `Microsoft.Crm.LocatorCache::AddEntryNoLock`
- size: `141`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3350`
- `0x3370`
- `0x3390`
- `0x33c0`

## callees

- `0x36b0`
- `0x3c70`
- `0x3ce0`
- `0x3d60`

## string_xrefs

- `0x36bb`: `CrmConfigDb`
- `0x36c4`: `CrmConfigDb`
- `0x36d3`: `CrmConfigDb`
- `0x36d8`: `CrmConfigDb`

## pseudocode

```c

```

## disassembly

```asm
0x36b0  ldarg.3
0x36b1  brtrue.s loc_36E8
0x36b3  ldc.i4.1
0x36b4  newarr   [mscorlib]System.String
0x36b9  dup
0x36ba  ldc.i4.0
0x36bb  ldstr    aCrmconfigdb// "CrmConfigDb"
0x36c0  stelem.ref
0x36c1  starg.s  3
0x36c3  ldarg.0
0x36c4  ldstr    aCrmconfigdb// "CrmConfigDb"
0x36c9  call     instance object Microsoft.Crm.LocatorCache::GetFromCache(string key)
0x36ce  stloc.0
0x36cf  ldloc.0
0x36d0  brtrue.s loc_36E8
0x36d2  ldarg.0
0x36d3  ldstr    aCrmconfigdb// "CrmConfigDb"
0x36d8  ldstr    aCrmconfigdb// "CrmConfigDb"
0x36dd  ldsfld   class [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy Microsoft.Crm.LocatorCache::NotRemovablePolicy
0x36e2  ldnull
0x36e3  call     instance void Microsoft.Crm.LocatorCache::InsertIntoCache(string key, object value, class [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy cacheItemPolicy, [opt] string[] dependencies)
0x36e8  ldarg.0
0x36e9  ldarg.1
0x36ea  ldarg.2
0x36eb  newobj   instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy::.ctor()
0x36f0  dup
0x36f1  call     class [System.Runtime.Caching]System.Runtime.Caching.CacheEntryRemovedCallback Microsoft.Crm.LocatorCache::get_CacheItemRemovedCallback()
0x36f6  callvirt instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy::set_RemovedCallback(class [System.Runtime.Caching]System.Runtime.Caching.CacheEntryRemovedCallback)
0x36fb  dup
0x36fc  ldc.i4.1
0x36fd  callvirt instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy::set_Priority(valuetype [System.Runtime.Caching]System.Runtime.Caching.CacheItemPriority)
0x3702  dup
0x3703  ldarg.s  4
0x3705  brtrue.s loc_3721
0x3707  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::get_UtcNow()
0x370c  ldc.r8   30.0
0x3715  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x371a  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Addition(valuetype [mscorlib]System.DateTimeOffset, valuetype [mscorlib]System.TimeSpan)
0x371f  br.s     loc_3726
0x3721  ldsfld   valuetype [mscorlib]System.DateTimeOffset [System.Runtime.Caching]System.Runtime.Caching.ObjectCache::InfiniteAbsoluteExpiration
0x3726  callvirt instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy::set_AbsoluteExpiration(valuetype [mscorlib]System.DateTimeOffset)
0x372b  dup
0x372c  ldsfld   valuetype [mscorlib]System.TimeSpan [System.Runtime.Caching]System.Runtime.Caching.ObjectCache::NoSlidingExpiration
0x3731  callvirt instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy::set_SlidingExpiration(valuetype [mscorlib]System.TimeSpan)
0x3736  ldarg.3
0x3737  call     instance void Microsoft.Crm.LocatorCache::InsertIntoCache(string key, object value, class [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy cacheItemPolicy, [opt] string[] dependencies)
0x373c  ret
```
