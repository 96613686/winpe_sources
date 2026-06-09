# __imp_load_WTSQueryUserToken

- ea: `0x180020dd1`
- end: `0x180020ddd`
- name: `__imp_load_WTSQueryUserToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020d2e`

## import_xrefs

- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180020dd1`

## pseudocode

```c
__int64 load_WTSQueryUserToken()
{
  return _tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll();
}

```

## disassembly

```asm
0x180020dd1  lea     rax, __imp_WTSQueryUserToken
0x180020dd8  jmp     __tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll
```
