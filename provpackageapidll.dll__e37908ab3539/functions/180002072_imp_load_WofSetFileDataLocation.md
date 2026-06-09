# __imp_load_WofSetFileDataLocation

- ea: `0x180002072`
- end: `0x18000207e`
- name: `__imp_load_WofSetFileDataLocation`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x180001fcf`

## import_xrefs

- `WOFUTIL!WofSetFileDataLocation` at `0x180002072`

## pseudocode

```c
__int64 load_WofSetFileDataLocation()
{
  return _tailMerge_wofutil_dll();
}

```

## disassembly

```asm
0x180002072  lea     rax, __imp_WofSetFileDataLocation
0x180002079  jmp     __tailMerge_wofutil_dll
```
