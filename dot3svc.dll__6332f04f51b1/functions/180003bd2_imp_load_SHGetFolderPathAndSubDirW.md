# __imp_load_SHGetFolderPathAndSubDirW

- ea: `0x180003bd2`
- end: `0x180003bde`
- name: `__imp_load_SHGetFolderPathAndSubDirW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003b41`

## import_xrefs

- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathAndSubDirW` at `0x180003bd2`

## pseudocode

```c
__int64 load_SHGetFolderPathAndSubDirW()
{
  return _tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003bd2  lea     rax, __imp_SHGetFolderPathAndSubDirW
0x180003bd9  jmp     __tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll
```
