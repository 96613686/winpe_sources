# __imp_load_EfsDllOnSessionChange

- ea: `0x1800023ed`
- end: `0x1800023f9`
- name: `__imp_load_EfsDllOnSessionChange`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllOnSessionChange` at `0x1800023ed`

## pseudocode

```c
__int64 load_EfsDllOnSessionChange()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800023ed  lea     rax, __imp_EfsDllOnSessionChange
0x1800023f4  jmp     __tailMerge_efscore_dll
```
