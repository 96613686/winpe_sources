# __imp_load_SHGetSpecialFolderPathW

- ea: `0x180012239`
- end: `0x180012245`
- name: `__imp_load_SHGetSpecialFolderPathW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012196`

## import_xrefs

- `api-ms-win-shell-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x180012239`

## pseudocode

```c
__int64 load_SHGetSpecialFolderPathW()
{
  return _tailMerge_api_ms_win_shell_shellfolders_l1_1_0_dll();
}

```

## disassembly

```asm
0x180012239  lea     rax, __imp_SHGetSpecialFolderPathW
0x180012240  jmp     __tailMerge_api_ms_win_shell_shellfolders_l1_1_0_dll
```
