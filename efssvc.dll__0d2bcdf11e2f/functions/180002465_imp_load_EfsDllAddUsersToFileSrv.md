# __imp_load_EfsDllAddUsersToFileSrv

- ea: `0x180002465`
- end: `0x180002471`
- name: `__imp_load_EfsDllAddUsersToFileSrv`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllAddUsersToFileSrv` at `0x180002465`

## pseudocode

```c
__int64 __fastcall load_EfsDllAddUsersToFileSrv(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002465  lea     rax, __imp_EfsDllAddUsersToFileSrv
0x18000246c  jmp     __tailMerge_efscore_dll
```
