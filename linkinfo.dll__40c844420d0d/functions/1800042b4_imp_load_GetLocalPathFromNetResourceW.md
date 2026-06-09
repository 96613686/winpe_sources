# __imp_load_GetLocalPathFromNetResourceW

- ea: `0x1800042b4`
- end: `0x1800042c0`
- name: `__imp_load_GetLocalPathFromNetResourceW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004223`

## import_xrefs

- `ext-ms-win-shell-ntshrui-l1-1-0!GetLocalPathFromNetResourceW` at `0x1800042b4`

## pseudocode

```c
__int64 load_GetLocalPathFromNetResourceW()
{
  return _tailMerge_ext_ms_win_shell_ntshrui_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800042b4  lea     rax, __imp_GetLocalPathFromNetResourceW
0x1800042bb  jmp     __tailMerge_ext_ms_win_shell_ntshrui_l1_1_0_dll
```
