# __imp_load_RasRenameEntryW

- ea: `0x180002aac`
- end: `0x180002ab8`
- name: `__imp_load_RasRenameEntryW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800029d3`

## import_xrefs

- `RASAPI32!RasRenameEntryW` at `0x180002aac`

## pseudocode

```c
__int64 load_RasRenameEntryW()
{
  return _tailMerge_rasapi32_dll();
}

```

## disassembly

```asm
0x180002aac  lea     rax, __imp_RasRenameEntryW
0x180002ab3  jmp     __tailMerge_rasapi32_dll
```
