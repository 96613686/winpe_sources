# __imp_load_EfsDllReadFileRaw

- ea: `0x180002489`
- end: `0x180002495`
- name: `__imp_load_EfsDllReadFileRaw`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllReadFileRaw` at `0x180002489`

## pseudocode

```c
__int64 load_EfsDllReadFileRaw()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002489  lea     rax, __imp_EfsDllReadFileRaw
0x180002490  jmp     __tailMerge_efscore_dll
```
