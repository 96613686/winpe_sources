# __imp_load_DevCreateObjectQuery

- ea: `0x18004db30`
- end: `0x18004db3c`
- name: `__imp_load_DevCreateObjectQuery`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18004da8d`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18004db30`

## pseudocode

```c
__int64 load_DevCreateObjectQuery()
{
  return _tailMerge_api_ms_win_devices_query_l1_1_0_dll();
}

```

## disassembly

```asm
0x18004db30  lea     rax, __imp_DevCreateObjectQuery
0x18004db37  jmp     __tailMerge_api_ms_win_devices_query_l1_1_0_dll
```
