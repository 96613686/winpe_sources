# __imp_load_SHCreateMemStream

- ea: `0x180003d3b`
- end: `0x180003d47`
- name: `__imp_load_SHCreateMemStream`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003c98`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180003d3b`

## pseudocode

```c
__int64 load_SHCreateMemStream()
{
  return _tailMerge_api_ms_win_shcore_stream_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003d3b  lea     rax, __imp_SHCreateMemStream
0x180003d42  jmp     __tailMerge_api_ms_win_shcore_stream_l1_1_0_dll
```
