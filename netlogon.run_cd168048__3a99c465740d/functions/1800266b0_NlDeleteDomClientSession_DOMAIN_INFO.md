# NlDeleteDomClientSession(_DOMAIN_INFO *)

- ea: `0x1800266b0`
- end: `0x18002676b`
- name: `?NlDeleteDomClientSession@@YAXPEAU_DOMAIN_INFO@@@Z`
- size: `187`
- prototype: `void __fastcall(struct _DOMAIN_INFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800267ec`

## callees

- `0x18000c440`
- `0x18000de8c`
- `0x18000e0e0`
- `0x1800266b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180026721`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180026721`
- `ntdll!RtlLeaveCriticalSection` at `0x1800266fc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800266fc`
- `ntdll!RtlLeaveCriticalSection` at `0x18002675f`
- `ntdll!RtlEnterCriticalSection` at `0x1800266cc`
- `ntdll!RtlEnterCriticalSection` at `0x180026730`
- `ntdll!RtlEnterCriticalSection` at `0x1800266cc`
- `ntdll!RtlEnterCriticalSection` at `0x180026730`

## string_xrefs

- `0x180026708`: `NlDeleteDomClientSession: Sleeping a second waiting for ClientSession RefCount to zero.\n`

## pseudocode

```c

```
