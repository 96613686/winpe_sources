# __imp_load_EfsDllQueryUsersOnFileSrv

- ea: `0x1800027b3`
- end: `0x1800027bf`
- name: `__imp_load_EfsDllQueryUsersOnFileSrv`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllQueryUsersOnFileSrv` at `0x1800027b3`

## pseudocode

```c
__int64 load_EfsDllQueryUsersOnFileSrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800027b3  lea     rax, __imp_EfsDllQueryUsersOnFileSrv
0x1800027ba  jmp     __tailMerge_efscore_dll
```
