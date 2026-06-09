# __imp_load_EfsDllOnSessionChange

- ea: `0x18000241d`
- end: `0x180002429`
- name: `__imp_load_EfsDllOnSessionChange`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllOnSessionChange` at `0x18000241d`

## pseudocode

```c
__int64 load_EfsDllOnSessionChange()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000241d  lea     rax, __imp_EfsDllOnSessionChange
0x180002424  jmp     __tailMerge_efscore_dll
```
