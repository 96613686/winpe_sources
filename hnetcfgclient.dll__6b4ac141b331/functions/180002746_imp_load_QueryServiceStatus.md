# __imp_load_QueryServiceStatus

- ea: `0x180002746`
- end: `0x180002752`
- name: `__imp_load_QueryServiceStatus`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800026c7`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180002746`

## pseudocode

```c
__int64 load_QueryServiceStatus()
{
  return _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002746  lea     rax, __imp_QueryServiceStatus
0x18000274d  jmp     __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll
```
