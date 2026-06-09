# DfspDcRemoveRootReferralPerfCtrFromTable(_UNICODE_STRING *,DfsDomainRootPerfCtrSetInst *)

- ea: `0x14001d9a8`
- end: `0x14001da91`
- name: `?DfspDcRemoveRootReferralPerfCtrFromTable@@YAKPEAU_UNICODE_STRING@@PEAVDfsDomainRootPerfCtrSetInst@@@Z`
- size: `233`
- prototype: `unsigned int __fastcall(struct _UNICODE_STRING *, struct DfsDomainRootPerfCtrSetInst *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14001d384`

## callees

- `0x14000abc4`
- `0x14001d9a8`
- `0x14005b158`
- `0x14005b648`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x14001da72`
- `ntdll!RtlNtStatusToDosError` at `0x14001da72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001d9d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001d9d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001da54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001da54`

## pseudocode

```c

```
