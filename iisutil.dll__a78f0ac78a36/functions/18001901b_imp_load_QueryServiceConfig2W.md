# __imp_load_QueryServiceConfig2W

- ea: `0x18001901b`
- end: `0x180019027`
- name: `__imp_load_QueryServiceConfig2W`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180018f9c`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18001901b`

## pseudocode

```c
__int64 load_QueryServiceConfig2W()
{
  return _tailMerge_api_ms_win_service_management_l2_1_0_dll();
}

```

## disassembly

```asm
0x18001901b  lea     rax, __imp_QueryServiceConfig2W
0x180019022  jmp     __tailMerge_api_ms_win_service_management_l2_1_0_dll
```
