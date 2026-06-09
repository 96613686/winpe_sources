# __imp_load_EfsDllSsoFlushUserCache

- ea: `0x180002579`
- end: `0x180002585`
- name: `__imp_load_EfsDllSsoFlushUserCache`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllSsoFlushUserCache` at `0x180002579`

## pseudocode

```c
__int64 load_EfsDllSsoFlushUserCache()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002579  lea     rax, __imp_EfsDllSsoFlushUserCache
0x180002580  jmp     __tailMerge_efscore_dll
```
