# __imp_load_RasDeleteEntryW

- ea: `0x180002a52`
- end: `0x180002a5e`
- name: `__imp_load_RasDeleteEntryW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800029d3`

## import_xrefs

- `RASAPI32!RasDeleteEntryW` at `0x180002a52`

## pseudocode

```c
__int64 load_RasDeleteEntryW()
{
  return _tailMerge_rasapi32_dll();
}

```

## disassembly

```asm
0x180002a52  lea     rax, __imp_RasDeleteEntryW
0x180002a59  jmp     __tailMerge_rasapi32_dll
```
