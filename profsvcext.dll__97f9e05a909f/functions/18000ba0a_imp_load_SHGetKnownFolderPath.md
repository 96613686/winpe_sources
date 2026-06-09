# __imp_load_SHGetKnownFolderPath

- ea: `0x18000ba0a`
- end: `0x18000ba16`
- name: `__imp_load_SHGetKnownFolderPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b979`

## import_xrefs

- `SHELL32!SHGetKnownFolderPath` at `0x18000ba0a`

## pseudocode

```c
__int64 load_SHGetKnownFolderPath()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x18000ba0a  lea     rax, __imp_SHGetKnownFolderPath
0x18000ba11  jmp     __tailMerge_shell32_dll
```
