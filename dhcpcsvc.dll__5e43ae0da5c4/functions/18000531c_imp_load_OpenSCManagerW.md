# __imp_load_OpenSCManagerW

- ea: `0x18000531c`
- end: `0x180005328`
- name: `__imp_load_OpenSCManagerW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000529d`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000531c`

## pseudocode

```c
__int64 load_OpenSCManagerW()
{
  return _tailMerge_api_ms_win_service_management_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000531c  lea     rax, __imp_OpenSCManagerW
0x180005323  jmp     __tailMerge_api_ms_win_service_management_l1_1_0_dll
```
