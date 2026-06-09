# __imp_load_TaskDialog

- ea: `0x180002b1e`
- end: `0x180002b2a`
- name: `__imp_load_TaskDialog`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002a9f`

## import_xrefs

- `COMCTL32!__imp_TaskDialog` at `0x180002b1e`

## pseudocode

```c
__int64 load_TaskDialog()
{
  return _tailMerge_comctl32_dll();
}

```

## disassembly

```asm
0x180002b1e  lea     rax, __imp_TaskDialog
0x180002b25  jmp     __tailMerge_comctl32_dll
```
