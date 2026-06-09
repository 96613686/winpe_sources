# __imp_load_SHGetFolderPathAndSubDirW

- ea: `0x1800019bf`
- end: `0x1800019cb`
- name: `__imp_load_SHGetFolderPathAndSubDirW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001940`

## import_xrefs

- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathAndSubDirW` at `0x1800019bf`

## pseudocode

```c
__int64 load_SHGetFolderPathAndSubDirW()
{
  return _tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800019bf  lea     rax, __imp_SHGetFolderPathAndSubDirW
0x1800019c6  jmp     __tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll
```
