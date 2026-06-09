# __imp_load_StartServiceA

- ea: `0x18001578c`
- end: `0x180015798`
- name: `__imp_load_StartServiceA`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800156fb`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x18001578c`

## pseudocode

```c
__int64 load_StartServiceA()
{
  return _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001578c  lea     rax, __imp_StartServiceA
0x180015793  jmp     __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll
```
