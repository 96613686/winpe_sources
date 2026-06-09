# __imp_load_IppTryGetPcFromCache

- ea: `0x180010637`
- end: `0x180010643`
- name: `__imp_load_IppTryGetPcFromCache`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800105a6`

## import_xrefs

- `IppCommon!IppTryGetPcFromCache` at `0x180010637`

## pseudocode

```c
__int64 load_IppTryGetPcFromCache()
{
  return _tailMerge_ippcommon_dll();
}

```

## disassembly

```asm
0x180010637  lea     rax, __imp_IppTryGetPcFromCache
0x18001063e  jmp     __tailMerge_ippcommon_dll
```
