# __imp_load_SHGetFolderPathW

- ea: `0x180002e76`
- end: `0x180002e82`
- name: `__imp_load_SHGetFolderPathW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002df7`

## import_xrefs

- `SHELL32!SHGetFolderPathW` at `0x180002e76`

## pseudocode

```c
__int64 load_SHGetFolderPathW()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x180002e76  lea     rax, __imp_SHGetFolderPathW
0x180002e7d  jmp     __tailMerge_shell32_dll
```
