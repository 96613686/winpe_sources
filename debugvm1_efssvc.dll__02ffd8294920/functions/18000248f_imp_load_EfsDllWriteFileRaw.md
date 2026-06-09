# __imp_load_EfsDllWriteFileRaw

- ea: `0x18000248f`
- end: `0x18000249b`
- name: `__imp_load_EfsDllWriteFileRaw`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllWriteFileRaw` at `0x18000248f`

## pseudocode

```c
__int64 load_EfsDllWriteFileRaw()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000248f  lea     rax, __imp_EfsDllWriteFileRaw
0x180002496  jmp     __tailMerge_efscore_dll
```
