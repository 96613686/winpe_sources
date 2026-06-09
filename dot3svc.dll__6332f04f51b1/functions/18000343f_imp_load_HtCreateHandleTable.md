# __imp_load_HtCreateHandleTable

- ea: `0x18000343f`
- end: `0x18000344b`
- name: `__imp_load_HtCreateHandleTable`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800033c0`

## import_xrefs

- `MobileNetworking!HtCreateHandleTable` at `0x18000343f`

## pseudocode

```c
__int64 load_HtCreateHandleTable()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x18000343f  lea     rax, __imp_HtCreateHandleTable
0x180003446  jmp     __tailMerge_mobilenetworking_dll
```
