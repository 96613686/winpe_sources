# __imp_load_OpenDriver

- ea: `0x18000aaf2`
- end: `0x18000aafe`
- name: `__imp_load_OpenDriver`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000aa61`

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!OpenDriver` at `0x18000aaf2`

## pseudocode

```c
__int64 load_OpenDriver()
{
  return _tailMerge_api_ms_win_mm_misc_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000aaf2  lea     rax, __imp_OpenDriver
0x18000aaf9  jmp     __tailMerge_api_ms_win_mm_misc_l1_1_0_dll
```
