# NlDeleteDomClientSession(_DOMAIN_INFO *)

- ea: `0x1800255f4`
- end: `0x180025692`
- name: `?NlDeleteDomClientSession@@YAXPEAU_DOMAIN_INFO@@@Z`
- size: `158`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180025708`

## callees

- `0x18000bd98`
- `0x18000d874`
- `0x18000da94`
- `0x1800255f4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180025659`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180025659`
- `ntdll!RtlLeaveCriticalSection` at `0x18002563a`
- `ntdll!RtlLeaveCriticalSection` at `0x18002563a`
- `ntdll!RtlLeaveCriticalSection` at `0x18002568b`
- `ntdll!RtlEnterCriticalSection` at `0x180025610`
- `ntdll!RtlEnterCriticalSection` at `0x180025662`
- `ntdll!RtlEnterCriticalSection` at `0x180025610`
- `ntdll!RtlEnterCriticalSection` at `0x180025662`

## string_xrefs

- `0x180025640`: `NlDeleteDomClientSession: Sleeping a second waiting for ClientSession RefCount to zero.\n`

## pseudocode

```c

```
