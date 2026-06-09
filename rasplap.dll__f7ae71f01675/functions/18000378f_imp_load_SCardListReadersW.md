# __imp_load_SCardListReadersW

- ea: `0x18000378f`
- end: `0x18000379b`
- name: `__imp_load_SCardListReadersW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800036fe`

## import_xrefs

- `WinSCard!SCardListReadersW` at `0x18000378f`

## pseudocode

```c
__int64 load_SCardListReadersW()
{
  return _tailMerge_winscard_dll();
}

```

## disassembly

```asm
0x18000378f  lea     rax, __imp_SCardListReadersW
0x180003796  jmp     __tailMerge_winscard_dll
```
