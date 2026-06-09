# __imp_load_OpenSCManagerA

- ea: `0x1800157b0`
- end: `0x1800157bc`
- name: `__imp_load_OpenSCManagerA`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800156fb`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x1800157b0`

## pseudocode

```c
__int64 load_OpenSCManagerA()
{
  return _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800157b0  lea     rax, __imp_OpenSCManagerA
0x1800157b7  jmp     __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll
```
