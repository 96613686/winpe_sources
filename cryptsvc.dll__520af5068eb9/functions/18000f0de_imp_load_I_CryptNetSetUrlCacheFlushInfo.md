# __imp_load_I_CryptNetSetUrlCacheFlushInfo

- ea: `0x18000f0de`
- end: `0x18000f0ea`
- name: `__imp_load_I_CryptNetSetUrlCacheFlushInfo`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f03b`

## import_xrefs

- `CRYPTNET!I_CryptNetSetUrlCacheFlushInfo` at `0x18000f0de`

## pseudocode

```c
__int64 load_I_CryptNetSetUrlCacheFlushInfo()
{
  return _tailMerge_cryptnet_dll();
}

```

## disassembly

```asm
0x18000f0de  lea     rax, __imp_I_CryptNetSetUrlCacheFlushInfo
0x18000f0e5  jmp     __tailMerge_cryptnet_dll
```
