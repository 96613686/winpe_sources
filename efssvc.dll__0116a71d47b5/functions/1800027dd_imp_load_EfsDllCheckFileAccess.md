# __imp_load_EfsDllCheckFileAccess

- ea: `0x1800027dd`
- end: `0x1800027e9`
- name: `__imp_load_EfsDllCheckFileAccess`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllCheckFileAccess` at `0x1800027dd`

## pseudocode

```c
__int64 load_EfsDllCheckFileAccess()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800027dd  lea     rax, __imp_EfsDllCheckFileAccess
0x1800027e4  jmp     __tailMerge_efscore_dll
```
