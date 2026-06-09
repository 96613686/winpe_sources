# __imp_load_EfsDllEncryptFileSrv

- ea: `0x180002543`
- end: `0x18000254f`
- name: `__imp_load_EfsDllEncryptFileSrv`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllEncryptFileSrv` at `0x180002543`

## pseudocode

```c
__int64 load_EfsDllEncryptFileSrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002543  lea     rax, __imp_EfsDllEncryptFileSrv
0x18000254a  jmp     __tailMerge_efscore_dll
```
