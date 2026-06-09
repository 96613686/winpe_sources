# __imp_load_CreateWriterEx

- ea: `0x18000cc55`
- end: `0x18000cc61`
- name: `__imp_load_CreateWriterEx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000cbd6`

## import_xrefs

- `ext-ms-win-fs-vssapi-l1-1-0!CreateWriterEx` at `0x18000cc55`

## pseudocode

```c
__int64 load_CreateWriterEx()
{
  return _tailMerge_ext_ms_win_fs_vssapi_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000cc55  lea     rax, __imp_CreateWriterEx
0x18000cc5c  jmp     __tailMerge_ext_ms_win_fs_vssapi_l1_1_0_dll
```
