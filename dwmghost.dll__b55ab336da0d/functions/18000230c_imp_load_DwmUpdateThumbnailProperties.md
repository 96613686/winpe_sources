# __imp_load_DwmUpdateThumbnailProperties

- ea: `0x18000230c`
- end: `0x180002318`
- name: `__imp_load_DwmUpdateThumbnailProperties`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18000227b`

## import_xrefs

- `dwmapi!DwmUpdateThumbnailProperties` at `0x18000230c`

## pseudocode

```c
__int64 load_DwmUpdateThumbnailProperties()
{
  return _tailMerge_dwmapi_dll();
}

```

## disassembly

```asm
0x18000230c  lea     rax, __imp_DwmUpdateThumbnailProperties
0x180002313  jmp     __tailMerge_dwmapi_dll
```
