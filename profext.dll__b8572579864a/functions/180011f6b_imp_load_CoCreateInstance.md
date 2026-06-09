# __imp_load_CoCreateInstance

- ea: `0x180011f6b`
- end: `0x180011f77`
- name: `__imp_load_CoCreateInstance`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011d10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011f6b`

## pseudocode

```c
__int64 load_CoCreateInstance()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x180011f6b  lea     rax, __imp_CoCreateInstance
0x180011f72  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
