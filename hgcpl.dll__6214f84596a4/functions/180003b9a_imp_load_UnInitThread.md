# __imp_load_UnInitThread

- ea: `0x180003b9a`
- end: `0x180003ba6`
- name: `__imp_load_UnInitThread`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800030ff`

## import_xrefs

- `DUI70!UnInitThread` at `0x180003b9a`

## pseudocode

```c
__int64 load_UnInitThread()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180003b9a  lea     rax, __imp_UnInitThread
0x180003ba1  jmp     __tailMerge_dui70_dll
```
