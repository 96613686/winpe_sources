# __imp_load_EfsDllShareDecline

- ea: `0x180002735`
- end: `0x180002741`
- name: `__imp_load_EfsDllShareDecline`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllShareDecline` at `0x180002735`

## pseudocode

```c
__int64 load_EfsDllShareDecline()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002735  lea     rax, __imp_EfsDllShareDecline
0x18000273c  jmp     __tailMerge_efscore_dll
```
