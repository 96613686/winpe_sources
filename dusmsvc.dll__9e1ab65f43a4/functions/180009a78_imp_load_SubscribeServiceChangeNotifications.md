# __imp_load_SubscribeServiceChangeNotifications

- ea: `0x180009a78`
- end: `0x180009a84`
- name: `__imp_load_SubscribeServiceChangeNotifications`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800099f9`

## import_xrefs

- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180009a78`

## pseudocode

```c
__int64 load_SubscribeServiceChangeNotifications()
{
  return _tailMerge_api_ms_win_service_private_l1_1_0_dll();
}

```

## disassembly

```asm
0x180009a78  lea     rax, __imp_SubscribeServiceChangeNotifications
0x180009a7f  jmp     __tailMerge_api_ms_win_service_private_l1_1_0_dll
```
