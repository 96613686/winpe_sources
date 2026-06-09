# __imp_load_CreateCompatibleDC

- ea: `0x1800022a7`
- end: `0x1800022b3`
- name: `__imp_load_CreateCompatibleDC`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002228`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1800022a7`

## pseudocode

```c
__int64 load_CreateCompatibleDC()
{
  return _tailMerge_ext_ms_win_gdi_dc_create_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800022a7  lea     rax, __imp_CreateCompatibleDC
0x1800022ae  jmp     __tailMerge_ext_ms_win_gdi_dc_create_l1_1_0_dll
```
