# __imp_load_NotifyServiceStatusChangeA

- ea: `0x1800162ae`
- end: `0x1800162ba`
- name: `__imp_load_NotifyServiceStatusChangeA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18001609b`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!NotifyServiceStatusChangeA` at `0x1800162ae`

## pseudocode

```c
__int64 load_NotifyServiceStatusChangeA()
{
  return _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800162ae  lea     rax, __imp_NotifyServiceStatusChangeA
0x1800162b5  jmp     __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll
```
