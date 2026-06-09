# __imp_load_CloseServiceHandle

- ea: `0x180009a9c`
- end: `0x180009aa8`
- name: `__imp_load_CloseServiceHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000995c`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180009a9c`

## pseudocode

```c
__int64 load_CloseServiceHandle()
{
  return _tailMerge_api_ms_win_service_management_l1_1_0_dll();
}

```

## disassembly

```asm
0x180009a9c  lea     rax, __imp_CloseServiceHandle
0x180009aa3  jmp     __tailMerge_api_ms_win_service_management_l1_1_0_dll
```
