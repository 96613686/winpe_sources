# __imp_load_NotifyServiceStatusChangeA

- ea: `0x18001590e`
- end: `0x18001591a`
- name: `__imp_load_NotifyServiceStatusChangeA`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800156fb`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!NotifyServiceStatusChangeA` at `0x18001590e`

## pseudocode

```c
__int64 load_NotifyServiceStatusChangeA()
{
  return _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001590e  lea     rax, __imp_NotifyServiceStatusChangeA
0x180015915  jmp     __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll
```
