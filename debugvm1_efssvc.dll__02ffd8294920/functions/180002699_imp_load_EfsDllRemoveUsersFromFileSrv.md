# __imp_load_EfsDllRemoveUsersFromFileSrv

- ea: `0x180002699`
- end: `0x1800026a5`
- name: `__imp_load_EfsDllRemoveUsersFromFileSrv`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllRemoveUsersFromFileSrv` at `0x180002699`

## pseudocode

```c
__int64 load_EfsDllRemoveUsersFromFileSrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002699  lea     rax, __imp_EfsDllRemoveUsersFromFileSrv
0x1800026a0  jmp     __tailMerge_efscore_dll
```
