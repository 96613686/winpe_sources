# __imp_load_GetWindowThreadProcessId

- ea: `0x18000206f`
- end: `0x18000207b`
- name: `__imp_load_GetWindowThreadProcessId`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001d2f`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000206f`

## pseudocode

```c
__int64 load_GetWindowThreadProcessId()
{
  return _tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000206f  lea     rax, __imp_GetWindowThreadProcessId
0x180002076  jmp     __tailMerge_ext_ms_win_ntuser_window_l1_1_0_dll
```
