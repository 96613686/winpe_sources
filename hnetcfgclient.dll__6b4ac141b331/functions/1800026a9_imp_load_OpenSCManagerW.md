# __imp_load_OpenSCManagerW

- ea: `0x1800026a9`
- end: `0x1800026b5`
- name: `__imp_load_OpenSCManagerW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000262a`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800026a9`

## pseudocode

```c
__int64 load_OpenSCManagerW()
{
  return _tailMerge_api_ms_win_service_management_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800026a9  lea     rax, __imp_OpenSCManagerW
0x1800026b0  jmp     __tailMerge_api_ms_win_service_management_l1_1_0_dll
```
