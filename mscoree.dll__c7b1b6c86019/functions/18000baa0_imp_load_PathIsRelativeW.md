# __imp_load_PathIsRelativeW

- ea: `0x18000baa0`
- end: `0x18000baac`
- name: `__imp_load_PathIsRelativeW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ba21`

## import_xrefs

- `SHLWAPI!PathIsRelativeW` at `0x18000baa0`

## pseudocode

```c
__int64 load_PathIsRelativeW()
{
  return _tailMerge_shlwapi_dll();
}

```

## disassembly

```asm
0x18000baa0  lea     rax, __imp_PathIsRelativeW
0x18000baa7  jmp     __tailMerge_shlwapi_dll
```
