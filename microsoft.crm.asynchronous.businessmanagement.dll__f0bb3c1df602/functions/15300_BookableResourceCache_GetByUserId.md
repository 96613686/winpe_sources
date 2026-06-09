# BookableResourceCache::GetByUserId

- ea: `0x15300`
- end: `0x15313`
- name: `BookableResourceCache::GetByUserId`
- size: `19`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x8780`
- `0x14b50`
- `0x15330`

## pseudocode

```c

```

## disassembly

```asm
0x15300  ldnull
0x15301  stloc.0
0x15302  ldarg.0
0x15303  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData> BookableResourceCache::cacheByUserId
0x15308  ldarg.1
0x15309  ldloca.s 0
0x1530b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData>::TryGetValue(var<u1>, !!T0)
0x15310  pop
0x15311  ldloc.0
0x15312  ret
```
