# __imp_load_SHCreateDirectoryExW

- ea: `0x18000b9f8`
- end: `0x18000ba04`
- name: `__imp_load_SHCreateDirectoryExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b979`

## import_xrefs

- `SHELL32!SHCreateDirectoryExW` at `0x18000b9f8`

## pseudocode

```c
__int64 load_SHCreateDirectoryExW()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x18000b9f8  lea     rax, __imp_SHCreateDirectoryExW
0x18000b9ff  jmp     __tailMerge_shell32_dll
```
