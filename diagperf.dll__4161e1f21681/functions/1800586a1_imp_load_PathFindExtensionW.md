# __imp_load_PathFindExtensionW

- ea: `0x1800586a1`
- end: `0x1800586ad`
- name: `__imp_load_PathFindExtensionW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180058622`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x1800586a1`

## pseudocode

```c
__int64 load_PathFindExtensionW()
{
  return _tailMerge_shlwapi_dll();
}

```

## disassembly

```asm
0x1800586a1  lea     rax, __imp_PathFindExtensionW
0x1800586a8  jmp     __tailMerge_shlwapi_dll
```
