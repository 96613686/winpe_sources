# __imp_load_SHCreateStreamOnFileEx

- ea: `0x1400021ea`
- end: `0x1400021f6`
- name: `__imp_load_SHCreateStreamOnFileEx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14000216b`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1400021ea`

## pseudocode

```c
__int64 load_SHCreateStreamOnFileEx()
{
  return _tailMerge_api_ms_win_shcore_stream_l1_1_0_dll();
}

```

## disassembly

```asm
0x1400021ea  lea     rax, __imp_SHCreateStreamOnFileEx
0x1400021f1  jmp     __tailMerge_api_ms_win_shcore_stream_l1_1_0_dll
```
