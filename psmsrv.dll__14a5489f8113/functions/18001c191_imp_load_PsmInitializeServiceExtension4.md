# __imp_load_PsmInitializeServiceExtension4

- ea: `0x18001c191`
- end: `0x18001c19d`
- name: `__imp_load_PsmInitializeServiceExtension4`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18001c112`

## import_xrefs

- `ext-ms-win-core-psm-service-l1-1-3!PsmInitializeServiceExtension4` at `0x18001c191`

## pseudocode

```c
__int64 load_PsmInitializeServiceExtension4()
{
  return _tailMerge_ext_ms_win_core_psm_service_l1_1_3_dll();
}

```

## disassembly

```asm
0x18001c191  lea     rax, __imp_PsmInitializeServiceExtension4
0x18001c198  jmp     __tailMerge_ext_ms_win_core_psm_service_l1_1_3_dll
```
