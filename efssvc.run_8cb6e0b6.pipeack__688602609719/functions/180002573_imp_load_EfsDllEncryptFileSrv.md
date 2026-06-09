# __imp_load_EfsDllEncryptFileSrv

- ea: `0x180002573`
- end: `0x18000257f`
- name: `__imp_load_EfsDllEncryptFileSrv`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllEncryptFileSrv` at `0x180002573`

## pseudocode

```c
__int64 load_EfsDllEncryptFileSrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002573  lea     rax, __imp_EfsDllEncryptFileSrv
0x18000257a  jmp     __tailMerge_efscore_dll
```
