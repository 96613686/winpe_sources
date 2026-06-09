# __imp_load_QueryServiceStatus

- ea: `0x1800161ed`
- end: `0x1800161f9`
- name: `__imp_load_QueryServiceStatus`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18001609b`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800161ed`

## pseudocode

```c
__int64 load_QueryServiceStatus()
{
  return _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800161ed  lea     rax, __imp_QueryServiceStatus
0x1800161f4  jmp     __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll
```
