# __imp_load_EfsDllFileKeyInfoSrv

- ea: `0x180002723`
- end: `0x18000272f`
- name: `__imp_load_EfsDllFileKeyInfoSrv`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllFileKeyInfoSrv` at `0x180002723`

## pseudocode

```c
__int64 load_EfsDllFileKeyInfoSrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002723  lea     rax, __imp_EfsDllFileKeyInfoSrv
0x18000272a  jmp     __tailMerge_efscore_dll
```
