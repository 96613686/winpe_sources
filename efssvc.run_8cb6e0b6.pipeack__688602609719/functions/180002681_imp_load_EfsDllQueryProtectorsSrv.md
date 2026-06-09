# __imp_load_EfsDllQueryProtectorsSrv

- ea: `0x180002681`
- end: `0x18000268d`
- name: `__imp_load_EfsDllQueryProtectorsSrv`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllQueryProtectorsSrv` at `0x180002681`

## pseudocode

```c
__int64 load_EfsDllQueryProtectorsSrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002681  lea     rax, __imp_EfsDllQueryProtectorsSrv
0x180002688  jmp     __tailMerge_efscore_dll
```
