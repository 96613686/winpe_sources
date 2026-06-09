# __imp_load_PathCombineW

- ea: `0x18000bab2`
- end: `0x18000babe`
- name: `__imp_load_PathCombineW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18000ba21`

## import_xrefs

- `SHLWAPI!PathCombineW` at `0x18000bab2`

## pseudocode

```c
__int64 load_PathCombineW()
{
  return _tailMerge_shlwapi_dll();
}

```

## disassembly

```asm
0x18000bab2  lea     rax, __imp_PathCombineW
0x18000bab9  jmp     __tailMerge_shlwapi_dll
```
