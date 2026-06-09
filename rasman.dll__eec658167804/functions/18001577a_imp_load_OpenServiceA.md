# __imp_load_OpenServiceA

- ea: `0x18001577a`
- end: `0x180015786`
- name: `__imp_load_OpenServiceA`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800156fb`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18001577a`

## pseudocode

```c
__int64 load_OpenServiceA()
{
  return _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001577a  lea     rax, __imp_OpenServiceA
0x180015781  jmp     __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll
```
