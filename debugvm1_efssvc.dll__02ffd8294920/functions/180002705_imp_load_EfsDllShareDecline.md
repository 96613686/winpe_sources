# __imp_load_EfsDllShareDecline

- ea: `0x180002705`
- end: `0x180002711`
- name: `__imp_load_EfsDllShareDecline`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllShareDecline` at `0x180002705`

## pseudocode

```c
__int64 load_EfsDllShareDecline()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002705  lea     rax, __imp_EfsDllShareDecline
0x18000270c  jmp     __tailMerge_efscore_dll
```
