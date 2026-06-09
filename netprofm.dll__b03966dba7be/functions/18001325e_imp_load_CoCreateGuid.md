# __imp_load_CoCreateGuid

- ea: `0x18001325e`
- end: `0x18001326a`
- name: `__imp_load_CoCreateGuid`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800130be`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001325e`

## pseudocode

```c
__int64 load_CoCreateGuid()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001325e  lea     rax, __imp_CoCreateGuid
0x180013265  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
