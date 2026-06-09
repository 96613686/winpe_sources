# NlStopDomainThread(_DOMAIN_INFO *)

- ea: `0x180027900`
- end: `0x18002798a`
- name: `?NlStopDomainThread@@YAXPEAU_DOMAIN_INFO@@@Z`
- size: `138`
- prototype: `void __fastcall(struct _DOMAIN_INFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180025708`

## callees

- `0x18000bd98`
- `0x180027900`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027951`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027951`
- `ntdll!RtlLeaveCriticalSection` at `0x180027932`
- `ntdll!RtlLeaveCriticalSection` at `0x180027932`
- `ntdll!RtlLeaveCriticalSection` at `0x180027983`
- `ntdll!RtlEnterCriticalSection` at `0x180027910`
- `ntdll!RtlEnterCriticalSection` at `0x18002795e`
- `ntdll!RtlEnterCriticalSection` at `0x180027910`
- `ntdll!RtlEnterCriticalSection` at `0x18002795e`

## string_xrefs

- `0x180027938`: `NlStopDomainThread: Sleeping a second waiting for thread to stop.\n`

## pseudocode

```c

```
