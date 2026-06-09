# __imp_load_QueryUserToken

- ea: `0x180006f81`
- end: `0x180006f8d`
- name: `__imp_load_QueryUserToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006f02`

## import_xrefs

- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180006f81`

## pseudocode

```c
__int64 load_QueryUserToken()
{
  return _tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll();
}

```

## disassembly

```asm
0x180006f81  lea     rax, __imp_QueryUserToken
0x180006f88  jmp     __tailMerge_ext_ms_win_session_usertoken_l1_1_0_dll
```
