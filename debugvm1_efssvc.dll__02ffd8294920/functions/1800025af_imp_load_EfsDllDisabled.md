# __imp_load_EfsDllDisabled

- ea: `0x1800025af`
- end: `0x1800025bb`
- name: `__imp_load_EfsDllDisabled`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllDisabled` at `0x1800025af`

## pseudocode

```c
__int64 load_EfsDllDisabled()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800025af  lea     rax, __imp_EfsDllDisabled
0x1800025b6  jmp     __tailMerge_efscore_dll
```
