# __imp_load_QueryUserToken

- ea: `0x1800038cb`
- end: `0x1800038d7`
- name: `__imp_load_QueryUserToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000383a`

## import_xrefs

- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800038cb`

## pseudocode

```c
__int64 load_QueryUserToken()
{
  return _tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800038cb  lea     rax, __imp_QueryUserToken
0x1800038d2  jmp     __tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll
```
