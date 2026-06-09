# __imp_load_EfsDllErrorToNtStatus

- ea: `0x18000297d`
- end: `0x180002989`
- name: `__imp_load_EfsDllErrorToNtStatus`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000297d`

## pseudocode

```c
__int64 load_EfsDllErrorToNtStatus()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000297d  lea     rax, __imp_EfsDllErrorToNtStatus
0x180002984  jmp     __tailMerge_efscore_dll
```
