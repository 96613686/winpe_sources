# __imp_load_EfsDllOpenFileRaw

- ea: `0x1800026b7`
- end: `0x1800026c3`
- name: `__imp_load_EfsDllOpenFileRaw`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EfsDllOpenFileRaw` at `0x1800026b7`

## pseudocode

```c
__int64 load_EfsDllOpenFileRaw()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x1800026b7  lea     rax, __imp_EfsDllOpenFileRaw
0x1800026be  jmp     __tailMerge_efscore_dll
```
