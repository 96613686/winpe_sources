# __imp_load_InitThread

- ea: `0x180002528`
- end: `0x180002534`
- name: `__imp_load_InitThread`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800023b4`

## import_xrefs

- `DUI70!InitThread` at `0x180002528`

## pseudocode

```c
__int64 load_InitThread()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002528  lea     rax, __imp_InitThread
0x18000252f  jmp     __tailMerge_dui70_dll
```
