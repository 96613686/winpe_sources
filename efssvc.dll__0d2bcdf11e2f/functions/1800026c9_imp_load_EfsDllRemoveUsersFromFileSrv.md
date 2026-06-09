# __imp_load_EfsDllRemoveUsersFromFileSrv

- ea: `0x1800026c9`
- end: `0x1800026d5`
- name: `__imp_load_EfsDllRemoveUsersFromFileSrv`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllRemoveUsersFromFileSrv` at `0x1800026c9`

## pseudocode

```c
__int64 __fastcall load_EfsDllRemoveUsersFromFileSrv(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800026c9  lea     rax, __imp_EfsDllRemoveUsersFromFileSrv
0x1800026d0  jmp     __tailMerge_efscore_dll
```
