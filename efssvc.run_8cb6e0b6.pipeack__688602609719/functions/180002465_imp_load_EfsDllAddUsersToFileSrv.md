# __imp_load_EfsDllAddUsersToFileSrv

- ea: `0x180002465`
- end: `0x180002471`
- name: `__imp_load_EfsDllAddUsersToFileSrv`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllAddUsersToFileSrv` at `0x180002465`

## pseudocode

```c
__int64 load_EfsDllAddUsersToFileSrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002465  lea     rax, __imp_EfsDllAddUsersToFileSrv
0x18000246c  jmp     __tailMerge_efscore_dll
```
