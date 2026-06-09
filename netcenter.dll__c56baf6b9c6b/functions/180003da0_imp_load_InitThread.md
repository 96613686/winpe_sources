# __imp_load_InitThread

- ea: `0x180003da0`
- end: `0x180003dac`
- name: `__imp_load_InitThread`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002c86`

## import_xrefs

- `DUI70!InitThread` at `0x180003da0`

## pseudocode

```c
__int64 load_InitThread()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180003da0  lea     rax, __imp_InitThread
0x180003da7  jmp     __tailMerge_dui70_dll
```
