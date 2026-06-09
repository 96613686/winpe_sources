# __imp_load_GetNetResourceFromLocalPathW

- ea: `0x1800042a2`
- end: `0x1800042ae`
- name: `__imp_load_GetNetResourceFromLocalPathW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004223`

## import_xrefs

- `ext-ms-win-shell-ntshrui-l1-1-0!GetNetResourceFromLocalPathW` at `0x1800042a2`

## pseudocode

```c
__int64 load_GetNetResourceFromLocalPathW()
{
  return _tailMerge_ext_ms_win_shell_ntshrui_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800042a2  lea     rax, __imp_GetNetResourceFromLocalPathW
0x1800042a9  jmp     __tailMerge_ext_ms_win_shell_ntshrui_l1_1_0_dll
```
