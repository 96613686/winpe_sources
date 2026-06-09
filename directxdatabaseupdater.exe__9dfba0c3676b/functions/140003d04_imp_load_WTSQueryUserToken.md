# __imp_load_WTSQueryUserToken

- ea: `0x140003d04`
- end: `0x140003d10`
- name: `__imp_load_WTSQueryUserToken`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140003c1c`

## import_xrefs

- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x140003d04`

## pseudocode

```c
__int64 load_WTSQueryUserToken()
{
  return _tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll();
}

```

## disassembly

```asm
0x140003d04  lea     rax, __imp_WTSQueryUserToken
0x140003d0b  jmp     __tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll
```
