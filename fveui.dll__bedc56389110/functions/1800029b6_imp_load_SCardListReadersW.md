# __imp_load_SCardListReadersW

- ea: `0x1800029b6`
- end: `0x1800029c2`
- name: `__imp_load_SCardListReadersW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002901`

## import_xrefs

- `WinSCard!SCardListReadersW` at `0x1800029b6`

## pseudocode

```c
__int64 load_SCardListReadersW()
{
  return _tailMerge_winscard_dll();
}

```

## disassembly

```asm
0x1800029b6  lea     rax, __imp_SCardListReadersW
0x1800029bd  jmp     __tailMerge_winscard_dll
```
