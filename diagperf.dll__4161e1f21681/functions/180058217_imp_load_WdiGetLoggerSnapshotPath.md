# __imp_load_WdiGetLoggerSnapshotPath

- ea: `0x180058217`
- end: `0x180058223`
- name: `__imp_load_WdiGetLoggerSnapshotPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180058162`

## import_xrefs

- `wdi!WdiGetLoggerSnapshotPath` at `0x180058217`

## pseudocode

```c
__int64 load_WdiGetLoggerSnapshotPath()
{
  return _tailMerge_wdi_dll();
}

```

## disassembly

```asm
0x180058217  lea     rax, __imp_WdiGetLoggerSnapshotPath
0x18005821e  jmp     __tailMerge_wdi_dll
```
