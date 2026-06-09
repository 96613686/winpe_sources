# __imp_load_EfsDllSsoFlushUserCache

- ea: `0x1800025a9`
- end: `0x1800025b5`
- name: `__imp_load_EfsDllSsoFlushUserCache`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllSsoFlushUserCache` at `0x1800025a9`

## pseudocode

```c
__int64 load_EfsDllSsoFlushUserCache()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800025a9  lea     rax, __imp_EfsDllSsoFlushUserCache
0x1800025b0  jmp     __tailMerge_efscore_dll
```
