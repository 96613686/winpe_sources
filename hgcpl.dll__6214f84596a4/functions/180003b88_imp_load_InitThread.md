# __imp_load_InitThread

- ea: `0x180003b88`
- end: `0x180003b94`
- name: `__imp_load_InitThread`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800030ff`

## import_xrefs

- `DUI70!InitThread` at `0x180003b88`

## pseudocode

```c
__int64 load_InitThread()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180003b88  lea     rax, __imp_InitThread
0x180003b8f  jmp     __tailMerge_dui70_dll
```
