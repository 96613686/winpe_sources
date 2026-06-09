# KerbBuildTgtErrorReply(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_CONTEXT *,ulong *,uchar * *)

- ea: `0x180086c14`
- end: `0x180086d45`
- name: `?KerbBuildTgtErrorReply@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_KERB_CONTEXT@@PEAKPEAPEAE@Z`
- size: `305`
- prototype: `__int64 __fastcall(struct _KERB_LOGON_SESSION *, struct _KERB_CREDENTIAL *, struct _KERB_CONTEXT *, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002db10`
- `0x1800cfd78`

## callees

- `0x1800063e8`
- `0x180086c14`
- `0x180086d4c`
- `0x18008b70c`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180086cd0`
- `ntdll!RtlReleaseResource` at `0x180086cd0`
- `ntdll!RtlAcquireResourceExclusive` at `0x180086cb0`
- `ntdll!RtlAcquireResourceExclusive` at `0x180086cb0`
- `ntdll!RtlEnterCriticalSection` at `0x180086c3f`
- `ntdll!RtlEnterCriticalSection` at `0x180086c3f`
- `ntdll!RtlLeaveCriticalSection` at `0x180086c99`
- `ntdll!RtlLeaveCriticalSection` at `0x180086c99`

## string_xrefs

- `0x180086cfe`: `KerbHandleTgtRequest (TGT in error reply) saving ASC context->TicketCacheEntry, TGT is %p, was %p\n`

## pseudocode

```c

```
