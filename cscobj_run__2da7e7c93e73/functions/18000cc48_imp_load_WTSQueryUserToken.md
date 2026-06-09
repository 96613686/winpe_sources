# __imp_load_WTSQueryUserToken

- ea: `0x18000cc48`
- end: `0x18000cc54`
- name: `__imp_load_WTSQueryUserToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000cbc9`

## import_xrefs

- `WTSAPI32!WTSQueryUserToken` at `0x18000cc48`

## pseudocode

```c
__int64 load_WTSQueryUserToken()
{
  return _tailMerge_wtsapi32_dll();
}

```

## disassembly

```asm
0x18000cc48  lea     rax, __imp_WTSQueryUserToken
0x18000cc4f  jmp     __tailMerge_wtsapi32_dll
```
