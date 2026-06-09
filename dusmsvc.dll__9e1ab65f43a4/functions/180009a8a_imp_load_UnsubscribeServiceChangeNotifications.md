# __imp_load_UnsubscribeServiceChangeNotifications

- ea: `0x180009a8a`
- end: `0x180009a96`
- name: `__imp_load_UnsubscribeServiceChangeNotifications`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800099f9`

## import_xrefs

- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180009a8a`

## pseudocode

```c
__int64 load_UnsubscribeServiceChangeNotifications()
{
  return _tailMerge_api_ms_win_service_private_l1_1_0_dll();
}

```

## disassembly

```asm
0x180009a8a  lea     rax, __imp_UnsubscribeServiceChangeNotifications
0x180009a91  jmp     __tailMerge_api_ms_win_service_private_l1_1_0_dll
```
