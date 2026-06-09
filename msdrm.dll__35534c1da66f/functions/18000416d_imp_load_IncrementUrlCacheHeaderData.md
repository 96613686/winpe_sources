# __imp_load_IncrementUrlCacheHeaderData

- ea: `0x18000416d`
- end: `0x180004179`
- name: `__imp_load_IncrementUrlCacheHeaderData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004070`

## import_xrefs

- `WININET!IncrementUrlCacheHeaderData` at `0x18000416d`

## pseudocode

```c
__int64 load_IncrementUrlCacheHeaderData()
{
  return _tailMerge_wininet_dll();
}

```

## disassembly

```asm
0x18000416d  lea     rax, __imp_IncrementUrlCacheHeaderData
0x180004174  jmp     __tailMerge_wininet_dll
```
