# __imp_load_EfsDllGetLocalFileName

- ea: `0x18000250d`
- end: `0x180002519`
- name: `__imp_load_EfsDllGetLocalFileName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllGetLocalFileName` at `0x18000250d`

## pseudocode

```c
__int64 load_EfsDllGetLocalFileName()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000250d  lea     rax, __imp_EfsDllGetLocalFileName
0x180002514  jmp     __tailMerge_efscore_dll
```
