# __imp_load_WTSQueryUserToken

- ea: `0x140003078`
- end: `0x140003084`
- name: `__imp_load_WTSQueryUserToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002f91`

## import_xrefs

- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x140003078`

## pseudocode

```c
__int64 load_WTSQueryUserToken()
{
  return _tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll();
}

```

## disassembly

```asm
0x140003078  lea     rax, __imp_WTSQueryUserToken
0x14000307f  jmp     __tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll
```
