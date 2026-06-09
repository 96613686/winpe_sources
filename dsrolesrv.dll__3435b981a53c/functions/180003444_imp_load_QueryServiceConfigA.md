# __imp_load_QueryServiceConfigA

- ea: `0x180003444`
- end: `0x180003450`
- name: `__imp_load_QueryServiceConfigA`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180002550`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x180003444`

## pseudocode

```c
__int64 load_QueryServiceConfigA()
{
  return _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003444  lea     rax, __imp_QueryServiceConfigA
0x18000344b  jmp     __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll
```
