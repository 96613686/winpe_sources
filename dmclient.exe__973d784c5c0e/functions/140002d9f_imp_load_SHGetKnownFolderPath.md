# __imp_load_SHGetKnownFolderPath

- ea: `0x140002d9f`
- end: `0x140002dab`
- name: `__imp_load_SHGetKnownFolderPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002d20`

## import_xrefs

- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x140002d9f`

## pseudocode

```c
__int64 load_SHGetKnownFolderPath()
{
  return _tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll();
}

```

## disassembly

```asm
0x140002d9f  lea     rax, __imp_SHGetKnownFolderPath
0x140002da6  jmp     __tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll
```
