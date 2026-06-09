# KerbUpdateServerContext(_KERB_CONTEXT *,KERB_ENCRYPTED_TICKET *,KERB_AP_REQUEST *,_KERB_ENCRYPTION_KEY *,_LUID *,void * *,ulong,ulong,ulong,ulong,ulong,void * *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_LARGE_INTEGER *)

- ea: `0x18008a8cc`
- end: `0x18008aaf2`
- name: `?KerbUpdateServerContext@@YAJPEAU_KERB_CONTEXT@@PEAUKERB_ENCRYPTED_TICKET@@PEAUKERB_AP_REQUEST@@PEAU_KERB_ENCRYPTION_KEY@@PEAU_LUID@@PEAPEAXKKKKK5PEAU_UNICODE_STRING@@66PEAT_LARGE_INTEGER@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(struct _KERB_CONTEXT *, struct KERB_ENCRYPTED_TICKET *, struct KERB_AP_REQUEST *, struct _KERB_ENCRYPTION_KEY *, struct _LUID *, void **, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, void **, PUNICODE_STRING DestinationString, PUNICODE_STRING, PUNICODE_STRING, union _LARGE_INTEGER *)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x18002db10`
- `0x1800ce9ac`
- `0x1800cf66c`

## callees

- `0x1800072c0`
- `0x180016550`
- `0x180020e10`
- `0x1800210e0`
- `0x18006ba6c`
- `0x18008a8cc`
- `0x18008b70c`
- `0x1800c2288`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18008a957`
- `ntdll!RtlInitUnicodeString` at `0x18008a96f`
- `ntdll!RtlInitUnicodeString` at `0x18008a987`
- `ntdll!RtlInitUnicodeString` at `0x18008a957`
- `ntdll!RtlInitUnicodeString` at `0x18008a96f`
- `ntdll!RtlInitUnicodeString` at `0x18008a987`
- `ntdll!RtlReleaseResource` at `0x18008aadd`
- `ntdll!RtlReleaseResource` at `0x18008aadd`
- `ntdll!RtlAcquireResourceExclusive` at `0x18008a8ee`
- `ntdll!RtlAcquireResourceExclusive` at `0x18008a8ee`

## string_xrefs

- `0x18008a9fd`: `KerbUpdateServerContext ContextAttributes was %#x, now %#x\n`
- `0x18008aa0c`: `KerbUpdateServerContext`

## pseudocode

```c

```
