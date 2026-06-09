# __imp_load_EfsDllDecryptFileSrv

- ea: `0x18000249b`
- end: `0x1800024a7`
- name: `__imp_load_EfsDllDecryptFileSrv`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllDecryptFileSrv` at `0x18000249b`

## pseudocode

```c
__int64 load_EfsDllDecryptFileSrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000249b  lea     rax, __imp_EfsDllDecryptFileSrv
0x1800024a2  jmp     __tailMerge_efscore_dll
```
