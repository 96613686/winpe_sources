# __imp_load_PathUnquoteSpacesW

- ea: `0x140010c86`
- end: `0x140010c92`
- name: `__imp_load_PathUnquoteSpacesW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140010bad`

## import_xrefs

- `SHLWAPI!PathUnquoteSpacesW` at `0x140010c86`

## pseudocode

```c
__int64 load_PathUnquoteSpacesW()
{
  return _tailMerge_shlwapi_dll();
}

```

## disassembly

```asm
0x140010c86  lea     rax, __imp_PathUnquoteSpacesW
0x140010c8d  jmp     __tailMerge_shlwapi_dll
```
