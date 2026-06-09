# __imp_load_WTSQueryUserToken

- ea: `0x1800177c8`
- end: `0x1800177d4`
- name: `__imp_load_WTSQueryUserToken`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180017713`

## import_xrefs

- `WTSAPI32!WTSQueryUserToken` at `0x1800177c8`

## pseudocode

```c
__int64 load_WTSQueryUserToken()
{
  return _tailMerge_wtsapi32_dll();
}

```

## disassembly

```asm
0x1800177c8  lea     rax, __imp_WTSQueryUserToken
0x1800177cf  jmp     __tailMerge_wtsapi32_dll
```
