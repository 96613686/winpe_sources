# __imp_load_EfsDllErrorToNtStatus

- ea: `0x18000297d`
- end: `0x180002989`
- name: `__imp_load_EfsDllErrorToNtStatus`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000297d`

## pseudocode

```c
__int64 __fastcall load_EfsDllErrorToNtStatus(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000297d  lea     rax, __imp_EfsDllErrorToNtStatus
0x180002984  jmp     __tailMerge_efscore_dll
```
