# __imp_load_RemoveFileSystemUnion

- ea: `0x180003a69`
- end: `0x180003a75`
- name: `__imp_load_RemoveFileSystemUnion`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x1800039c6`

## import_xrefs

- `UNIONFSAPI!RemoveFileSystemUnion` at `0x180003a69`

## pseudocode

```c
__int64 load_RemoveFileSystemUnion()
{
  return _tailMerge_unionfsapi_dll();
}

```

## disassembly

```asm
0x180003a69  lea     rax, __imp_RemoveFileSystemUnion
0x180003a70  jmp     __tailMerge_unionfsapi_dll
```
