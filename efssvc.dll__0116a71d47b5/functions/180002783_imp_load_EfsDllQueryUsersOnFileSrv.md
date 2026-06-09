# __imp_load_EfsDllQueryUsersOnFileSrv

- ea: `0x180002783`
- end: `0x18000278f`
- name: `__imp_load_EfsDllQueryUsersOnFileSrv`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllQueryUsersOnFileSrv` at `0x180002783`

## pseudocode

```c
__int64 load_EfsDllQueryUsersOnFileSrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002783  lea     rax, __imp_EfsDllQueryUsersOnFileSrv
0x18000278a  jmp     __tailMerge_efscore_dll
```
