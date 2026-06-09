# __imp_load_OpenSCManagerW

- ea: `0x1800099db`
- end: `0x1800099e7`
- name: `__imp_load_OpenSCManagerW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000995c`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800099db`

## pseudocode

```c
__int64 load_OpenSCManagerW()
{
  return _tailMerge_api_ms_win_service_management_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800099db  lea     rax, __imp_OpenSCManagerW
0x1800099e2  jmp     __tailMerge_api_ms_win_service_management_l1_1_0_dll
```
