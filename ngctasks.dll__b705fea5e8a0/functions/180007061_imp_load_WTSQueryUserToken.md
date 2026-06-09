# __imp_load_WTSQueryUserToken

- ea: `0x180007061`
- end: `0x18000706d`
- name: `__imp_load_WTSQueryUserToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006fe2`

## import_xrefs

- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180007061`

## pseudocode

```c
__int64 load_WTSQueryUserToken()
{
  return _tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll();
}

```

## disassembly

```asm
0x180007061  lea     rax, __imp_WTSQueryUserToken
0x180007068  jmp     __tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll
```
