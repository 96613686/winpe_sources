# __imp_load_EfsDllFreeHeap

- ea: `0x18000278f`
- end: `0x18000279b`
- name: `__imp_load_EfsDllFreeHeap`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllFreeHeap` at `0x18000278f`

## pseudocode

```c
__int64 load_EfsDllFreeHeap()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000278f  lea     rax, __imp_EfsDllFreeHeap
0x180002796  jmp     __tailMerge_efscore_dll
```
