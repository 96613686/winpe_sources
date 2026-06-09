# __imp_load_OpenSCManagerA

- ea: `0x180016150`
- end: `0x18001615c`
- name: `__imp_load_OpenSCManagerA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18001609b`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180016150`

## pseudocode

```c
__int64 load_OpenSCManagerA()
{
  return _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll();
}

```

## disassembly

```asm
0x180016150  lea     rax, __imp_OpenSCManagerA
0x180016157  jmp     __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll
```
