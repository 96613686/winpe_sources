# __imp_load_DwmIsCompositionEnabled

- ea: `0x18000231e`
- end: `0x18000232a`
- name: `__imp_load_DwmIsCompositionEnabled`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000227b`

## import_xrefs

- `dwmapi!DwmIsCompositionEnabled` at `0x18000231e`

## pseudocode

```c
__int64 load_DwmIsCompositionEnabled()
{
  return _tailMerge_dwmapi_dll();
}

```

## disassembly

```asm
0x18000231e  lea     rax, __imp_DwmIsCompositionEnabled
0x180002325  jmp     __tailMerge_dwmapi_dll
```
