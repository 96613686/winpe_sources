# __imp_load_ChangeServiceConfigA

- ea: `0x180003420`
- end: `0x18000342c`
- name: `__imp_load_ChangeServiceConfigA`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180002550`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!ChangeServiceConfigA` at `0x180003420`

## pseudocode

```c
__int64 load_ChangeServiceConfigA()
{
  return _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003420  lea     rax, __imp_ChangeServiceConfigA
0x180003427  jmp     __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll
```
