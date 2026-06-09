# __imp_load_SHGetKnownFolderPath

- ea: `0x18004dd19`
- end: `0x18004dd25`
- name: `__imp_load_SHGetKnownFolderPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18004dc9a`

## import_xrefs

- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18004dd19`

## pseudocode

```c
__int64 load_SHGetKnownFolderPath()
{
  return _tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll();
}

```

## disassembly

```asm
0x18004dd19  lea     rax, __imp_SHGetKnownFolderPath
0x18004dd20  jmp     __tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll
```
