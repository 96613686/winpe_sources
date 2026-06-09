# __imp_load_EfsDllReadFileRaw

- ea: `0x180002459`
- end: `0x180002465`
- name: `__imp_load_EfsDllReadFileRaw`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllReadFileRaw` at `0x180002459`

## pseudocode

```c
__int64 load_EfsDllReadFileRaw()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002459  lea     rax, __imp_EfsDllReadFileRaw
0x180002460  jmp     __tailMerge_efscore_dll
```
