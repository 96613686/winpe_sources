# __imp_load_EfsDllFileKeyInfoSrv

- ea: `0x1800026f3`
- end: `0x1800026ff`
- name: `__imp_load_EfsDllFileKeyInfoSrv`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllFileKeyInfoSrv` at `0x1800026f3`

## pseudocode

```c
__int64 load_EfsDllFileKeyInfoSrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800026f3  lea     rax, __imp_EfsDllFileKeyInfoSrv
0x1800026fa  jmp     __tailMerge_efscore_dll
```
