# __imp_load_SHGetFolderPathW

- ea: `0x180058616`
- end: `0x180058622`
- name: `__imp_load_SHGetFolderPathW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800582c5`

## import_xrefs

- `SHELL32!SHGetFolderPathW` at `0x180058616`

## pseudocode

```c
__int64 load_SHGetFolderPathW()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x180058616  lea     rax, __imp_SHGetFolderPathW
0x18005861d  jmp     __tailMerge_shell32_dll
```
