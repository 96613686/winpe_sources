# __imp_load_ReadStorageProperties

- ea: `0x18004e949`
- end: `0x18004e955`
- name: `__imp_load_ReadStorageProperties`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18004e8ca`

## import_xrefs

- `ext-ms-win-ole32-oleautomation-l1-1-0!ReadStorageProperties` at `0x18004e949`

## pseudocode

```c
__int64 load_ReadStorageProperties()
{
  return _tailMerge_ext_ms_win_ole32_oleautomation_l1_1_0_dll();
}

```

## disassembly

```asm
0x18004e949  lea     rax, __imp_ReadStorageProperties
0x18004e950  jmp     __tailMerge_ext_ms_win_ole32_oleautomation_l1_1_0_dll
```
