# __imp_load_SHGetFolderPathW

- ea: `0x180012215`
- end: `0x180012221`
- name: `__imp_load_SHGetFolderPathW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012196`

## import_xrefs

- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180012215`

## pseudocode

```c
__int64 load_SHGetFolderPathW()
{
  return _tailMerge_api_ms_win_shell_shellfolders_l1_1_0_dll();
}

```

## disassembly

```asm
0x180012215  lea     rax, __imp_SHGetFolderPathW
0x18001221c  jmp     __tailMerge_api_ms_win_shell_shellfolders_l1_1_0_dll
```
