# __imp_load_EfsDllOpenFileRaw

- ea: `0x180002687`
- end: `0x180002693`
- name: `__imp_load_EfsDllOpenFileRaw`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllOpenFileRaw` at `0x180002687`

## pseudocode

```c
__int64 load_EfsDllOpenFileRaw()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002687  lea     rax, __imp_EfsDllOpenFileRaw
0x18000268e  jmp     __tailMerge_efscore_dll
```
