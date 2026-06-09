# NlStopDomainThread(_DOMAIN_INFO *)

- ea: `0x180028d0c`
- end: `0x180028db3`
- name: `?NlStopDomainThread@@YAXPEAU_DOMAIN_INFO@@@Z`
- size: `167`
- prototype: `void __fastcall(struct _DOMAIN_INFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800267ec`

## callees

- `0x18000c440`
- `0x180028d0c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028d69`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028d69`
- `ntdll!RtlLeaveCriticalSection` at `0x180028d44`
- `ntdll!RtlLeaveCriticalSection` at `0x180028d44`
- `ntdll!RtlLeaveCriticalSection` at `0x180028da7`
- `ntdll!RtlEnterCriticalSection` at `0x180028d1c`
- `ntdll!RtlEnterCriticalSection` at `0x180028d7c`
- `ntdll!RtlEnterCriticalSection` at `0x180028d1c`
- `ntdll!RtlEnterCriticalSection` at `0x180028d7c`

## string_xrefs

- `0x180028d50`: `NlStopDomainThread: Sleeping a second waiting for thread to stop.\n`

## pseudocode

```c

```
