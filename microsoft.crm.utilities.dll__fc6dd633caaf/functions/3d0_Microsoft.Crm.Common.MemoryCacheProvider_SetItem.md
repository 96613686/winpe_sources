# Microsoft.Crm.Common.MemoryCacheProvider::SetItem

- ea: `0x3d0`
- end: `0x425`
- name: `Microsoft.Crm.Common.MemoryCacheProvider::SetItem`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x380`
- `0x3d0`

## pseudocode

```c

```

## disassembly

```asm
0x3d0  ldarg.1
0x3d1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3d6  brfalse.s loc_3E3
0x3d8  ldstr    aKeyIsNullOrWhi// "Key is null or whitespace"
0x3dd  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3e2  throw
0x3e3  ldarg.2
0x3e4  brtrue.s loc_3F1
0x3e6  ldstr    aData// "data"
0x3eb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3f0  throw
0x3f1  newobj   instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy::.ctor()
0x3f6  stloc.0
0x3f7  ldloc.0
0x3f8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3fd  stloc.1
0x3fe  ldloca.s 1
0x400  ldarg.3
0x401  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0x406  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0x40b  callvirt instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy::set_AbsoluteExpiration(valuetype [mscorlib]System.DateTimeOffset)
0x410  ldarg.0
0x411  call     instance class [System.Runtime.Caching]System.Runtime.Caching.MemoryCache Microsoft.Crm.Common.MemoryCacheProvider::get_Cache()
0x416  ldarg.1
0x417  ldarg.2
0x418  newobj   instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItem::.ctor(string, object)
0x41d  ldloc.0
0x41e  callvirt instance bool [System.Runtime.Caching]System.Runtime.Caching.ObjectCache::Add(class [System.Runtime.Caching]System.Runtime.Caching.CacheItem, class [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy)
0x423  pop
0x424  ret
```
