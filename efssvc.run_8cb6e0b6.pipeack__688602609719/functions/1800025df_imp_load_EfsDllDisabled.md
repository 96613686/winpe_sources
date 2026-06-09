# __imp_load_EfsDllDisabled

- ea: `0x1800025df`
- end: `0x1800025eb`
- name: `__imp_load_EfsDllDisabled`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllDisabled` at `0x1800025df`

## pseudocode

```c
__int64 load_EfsDllDisabled()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800025df  lea     rax, __imp_EfsDllDisabled
0x1800025e6  jmp     __tailMerge_efscore_dll
```
