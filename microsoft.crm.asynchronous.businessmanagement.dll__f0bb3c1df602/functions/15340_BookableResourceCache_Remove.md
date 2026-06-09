# BookableResourceCache::Remove

- ea: `0x15340`
- end: `0x15370`
- name: `BookableResourceCache::Remove`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x15320`
- `0x15330`

## callees

- `0x15340`
- `0x178d0`
- `0x178f0`

## pseudocode

```c

```

## disassembly

```asm
0x15340  ldarg.1
0x15341  ldnull
0x15342  cgt.un
0x15344  stloc.0
0x15345  ldloc.0
0x15346  brfalse.s loc_1536E
0x15348  ldarg.0
0x15349  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData> BookableResourceCache::cacheByBookableResourceId
0x1534e  ldarg.1
0x1534f  callvirt instance valuetype [mscorlib]System.Guid CacheData::get_BookableResourceId()
0x15354  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData>::Remove(var<u1>)
0x15359  stloc.0
0x1535a  ldarg.0
0x1535b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData> BookableResourceCache::cacheByUserId
0x15360  ldarg.1
0x15361  callvirt instance valuetype [mscorlib]System.Guid CacheData::get_UserId()
0x15366  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData>::Remove(var<u1>)
0x1536b  ldloc.0
0x1536c  and
0x1536d  stloc.0
0x1536e  ldloc.0
0x1536f  ret
```
