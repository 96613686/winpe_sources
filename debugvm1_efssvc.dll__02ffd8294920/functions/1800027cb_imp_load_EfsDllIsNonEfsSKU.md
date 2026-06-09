# __imp_load_EfsDllIsNonEfsSKU

- ea: `0x1800027cb`
- end: `0x1800027d7`
- name: `__imp_load_EfsDllIsNonEfsSKU`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllIsNonEfsSKU` at `0x1800027cb`

## pseudocode

```c
__int64 load_EfsDllIsNonEfsSKU()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800027cb  lea     rax, __imp_EfsDllIsNonEfsSKU
0x1800027d2  jmp     __tailMerge_efscore_dll
```
