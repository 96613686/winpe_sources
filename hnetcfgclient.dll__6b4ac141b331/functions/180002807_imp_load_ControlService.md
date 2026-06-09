# __imp_load_ControlService

- ea: `0x180002807`
- end: `0x180002813`
- name: `__imp_load_ControlService`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800026c7`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180002807`

## pseudocode

```c
__int64 load_ControlService()
{
  return _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002807  lea     rax, __imp_ControlService
0x18000280e  jmp     __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll
```
