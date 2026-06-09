# __imp_load_SHCreateStreamOnFileEx

- ea: `0x1800032cc`
- end: `0x1800032d8`
- name: `__imp_load_SHCreateStreamOnFileEx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000324d`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800032cc`

## pseudocode

```c
__int64 load_SHCreateStreamOnFileEx()
{
  return _tailMerge_api_ms_win_shcore_stream_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800032cc  lea     rax, __imp_SHCreateStreamOnFileEx
0x1800032d3  jmp     __tailMerge_api_ms_win_shcore_stream_l1_1_0_dll
```
