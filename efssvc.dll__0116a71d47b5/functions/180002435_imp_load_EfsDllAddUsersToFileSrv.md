# __imp_load_EfsDllAddUsersToFileSrv

- ea: `0x180002435`
- end: `0x180002441`
- name: `__imp_load_EfsDllAddUsersToFileSrv`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllAddUsersToFileSrv` at `0x180002435`

## pseudocode

```c
__int64 load_EfsDllAddUsersToFileSrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002435  lea     rax, __imp_EfsDllAddUsersToFileSrv
0x18000243c  jmp     __tailMerge_efscore_dll
```
