# __imp_load_EfsDllQueryUsersOnFileSrv

- ea: `0x1800027b3`
- end: `0x1800027bf`
- name: `__imp_load_EfsDllQueryUsersOnFileSrv`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllQueryUsersOnFileSrv` at `0x1800027b3`

## pseudocode

```c
__int64 __fastcall load_EfsDllQueryUsersOnFileSrv(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800027b3  lea     rax, __imp_EfsDllQueryUsersOnFileSrv
0x1800027ba  jmp     __tailMerge_efscore_dll
```
