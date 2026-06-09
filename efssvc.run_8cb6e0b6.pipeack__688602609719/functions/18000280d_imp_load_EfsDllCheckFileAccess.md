# __imp_load_EfsDllCheckFileAccess

- ea: `0x18000280d`
- end: `0x180002819`
- name: `__imp_load_EfsDllCheckFileAccess`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllCheckFileAccess` at `0x18000280d`

## pseudocode

```c
__int64 load_EfsDllCheckFileAccess()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000280d  lea     rax, __imp_EfsDllCheckFileAccess
0x180002814  jmp     __tailMerge_efscore_dll
```
