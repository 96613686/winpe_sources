# BookableResourceCache::RemoveByUserId

- ea: `0x15330`
- end: `0x1533e`
- name: `BookableResourceCache::RemoveByUserId`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x8780`

## callees

- `0x15300`
- `0x15340`

## pseudocode

```c

```

## disassembly

```asm
0x15330  ldarg.0
0x15331  ldarg.0
0x15332  ldarg.1
0x15333  call     instance class CacheData BookableResourceCache::GetByUserId(valuetype [mscorlib]System.Guid userId)
0x15338  call     instance bool BookableResourceCache::Remove(class CacheData cacheData)
0x1533d  ret
```
