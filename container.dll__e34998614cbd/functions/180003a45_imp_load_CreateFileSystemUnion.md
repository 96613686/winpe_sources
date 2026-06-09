# __imp_load_CreateFileSystemUnion

- ea: `0x180003a45`
- end: `0x180003a51`
- name: `__imp_load_CreateFileSystemUnion`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x1800039c6`

## import_xrefs

- `UNIONFSAPI!CreateFileSystemUnion` at `0x180003a45`

## pseudocode

```c
__int64 load_CreateFileSystemUnion()
{
  return _tailMerge_unionfsapi_dll();
}

```

## disassembly

```asm
0x180003a45  lea     rax, __imp_CreateFileSystemUnion
0x180003a4c  jmp     __tailMerge_unionfsapi_dll
```
