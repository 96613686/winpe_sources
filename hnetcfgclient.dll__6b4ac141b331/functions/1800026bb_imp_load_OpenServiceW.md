# __imp_load_OpenServiceW

- ea: `0x1800026bb`
- end: `0x1800026c7`
- name: `__imp_load_OpenServiceW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000262a`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800026bb`

## pseudocode

```c
__int64 load_OpenServiceW()
{
  return _tailMerge_api_ms_win_service_management_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800026bb  lea     rax, __imp_OpenServiceW
0x1800026c2  jmp     __tailMerge_api_ms_win_service_management_l1_1_0_dll
```
