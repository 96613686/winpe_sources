# __imp_load_RegisterServiceCtrlHandlerExW

- ea: `0x18001d973`
- end: `0x18001d97f`
- name: `__imp_load_RegisterServiceCtrlHandlerExW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18001d8e2`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001d973`

## pseudocode

```c
__int64 load_RegisterServiceCtrlHandlerExW()
{
  return _tailMerge_api_ms_win_service_core_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001d973  lea     rax, __imp_RegisterServiceCtrlHandlerExW
0x18001d97a  jmp     __tailMerge_api_ms_win_service_core_l1_1_0_dll
```
