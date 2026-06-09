# __imp_load_WdiGetInstanceFilePath

- ea: `0x180058229`
- end: `0x180058235`
- name: `__imp_load_WdiGetInstanceFilePath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180058162`

## import_xrefs

- `wdi!WdiGetInstanceFilePath` at `0x180058229`

## pseudocode

```c
__int64 load_WdiGetInstanceFilePath()
{
  return _tailMerge_wdi_dll();
}

```

## disassembly

```asm
0x180058229  lea     rax, __imp_WdiGetInstanceFilePath
0x180058230  jmp     __tailMerge_wdi_dll
```
