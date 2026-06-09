# __imp_load_I_CryptNetSetUrlCachePreFetchInfo

- ea: `0x18000f0cc`
- end: `0x18000f0d8`
- name: `__imp_load_I_CryptNetSetUrlCachePreFetchInfo`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f03b`

## import_xrefs

- `CRYPTNET!I_CryptNetSetUrlCachePreFetchInfo` at `0x18000f0cc`

## pseudocode

```c
__int64 load_I_CryptNetSetUrlCachePreFetchInfo()
{
  return _tailMerge_cryptnet_dll();
}

```

## disassembly

```asm
0x18000f0cc  lea     rax, __imp_I_CryptNetSetUrlCachePreFetchInfo
0x18000f0d3  jmp     __tailMerge_cryptnet_dll
```
