# __imp_load_SHGetKnownFolderPath

- ea: `0x1800019d1`
- end: `0x1800019dd`
- name: `__imp_load_SHGetKnownFolderPath`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001940`

## import_xrefs

- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800019d1`

## pseudocode

```c
__int64 load_SHGetKnownFolderPath()
{
  return _tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800019d1  lea     rax, __imp_SHGetKnownFolderPath
0x1800019d8  jmp     __tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll
```
