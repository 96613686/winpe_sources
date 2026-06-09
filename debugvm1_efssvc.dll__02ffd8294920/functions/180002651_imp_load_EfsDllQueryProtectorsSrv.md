# __imp_load_EfsDllQueryProtectorsSrv

- ea: `0x180002651`
- end: `0x18000265d`
- name: `__imp_load_EfsDllQueryProtectorsSrv`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllQueryProtectorsSrv` at `0x180002651`

## pseudocode

```c
__int64 load_EfsDllQueryProtectorsSrv()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002651  lea     rax, __imp_EfsDllQueryProtectorsSrv
0x180002658  jmp     __tailMerge_efscore_dll
```
