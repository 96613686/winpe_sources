# __imp_load_TaskDialogIndirect

- ea: `0x180002b30`
- end: `0x180002b3c`
- name: `__imp_load_TaskDialogIndirect`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002a9f`

## import_xrefs

- `COMCTL32!__imp_TaskDialogIndirect` at `0x180002b30`

## pseudocode

```c
__int64 load_TaskDialogIndirect()
{
  return _tailMerge_comctl32_dll();
}

```

## disassembly

```asm
0x180002b30  lea     rax, __imp_TaskDialogIndirect
0x180002b37  jmp     __tailMerge_comctl32_dll
```
