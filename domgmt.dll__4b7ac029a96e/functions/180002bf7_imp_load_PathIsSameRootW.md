# __imp_load_PathIsSameRootW

- ea: `0x180002bf7`
- end: `0x180002c03`
- name: `__imp_load_PathIsSameRootW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002b78`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsSameRootW` at `0x180002bf7`

## pseudocode

```c
__int64 load_PathIsSameRootW()
{
  return _tailMerge_api_ms_win_core_shlwapi_legacy_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002bf7  lea     rax, __imp_PathIsSameRootW
0x180002bfe  jmp     __tailMerge_api_ms_win_core_shlwapi_legacy_l1_1_0_dll
```
