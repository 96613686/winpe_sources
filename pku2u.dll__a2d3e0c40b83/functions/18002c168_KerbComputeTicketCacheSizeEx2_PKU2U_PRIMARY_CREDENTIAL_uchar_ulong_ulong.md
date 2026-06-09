# KerbComputeTicketCacheSizeEx2(_PKU2U_PRIMARY_CREDENTIAL *,uchar,ulong *,ulong *)

- ea: `0x18002c168`
- end: `0x18002c21c`
- name: `?KerbComputeTicketCacheSizeEx2@@YAXPEAU_PKU2U_PRIMARY_CREDENTIAL@@EPEAK1@Z`
- size: `180`
- prototype: `void __fastcall(struct _PKU2U_PRIMARY_CREDENTIAL *, unsigned __int8, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c8c0`

## callees

- `0x18002c168`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002c215`
- `ntdll!RtlEnterCriticalSection` at `0x18002c199`
- `ntdll!RtlEnterCriticalSection` at `0x18002c199`

## pseudocode

```c

```
