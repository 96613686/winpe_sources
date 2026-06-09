# KerbGmsaBuildPasswords(_KERB_LOGON_SESSION *,_KERB_PRIMARY_CREDENTIAL *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *)

- ea: `0x1800aebbc`
- end: `0x1800af060`
- name: `?KerbGmsaBuildPasswords@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_PRIMARY_CREDENTIAL@@PEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@@Z`
- size: `1188`
- prototype: `int(struct _KERB_LOGON_SESSION *, struct _KERB_PRIMARY_CREDENTIAL *, struct _KERB_INTERNAL_NAME *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x180058f14`

## callees

- `0x1800068d0`
- `0x180010e90`
- `0x1800163a0`
- `0x180030f10`
- `0x18003392c`
- `0x18008b70c`
- `0x18008f354`
- `0x1800ad6a4`
- `0x1800ad920`
- `0x1800aebbc`
- `0x1800af2a0`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x1800aed71`
- `ntdll!RtlEqualUnicodeString` at `0x1800aed8d`
- `ntdll!RtlEqualUnicodeString` at `0x1800aedb0`
- `ntdll!RtlEqualUnicodeString` at `0x1800aed71`
- `ntdll!RtlEqualUnicodeString` at `0x1800aed8d`
- `ntdll!RtlEqualUnicodeString` at `0x1800aedb0`
- `ntdll!RtlEnterCriticalSection` at `0x1800aec0f`
- `ntdll!RtlEnterCriticalSection` at `0x1800aed42`
- `ntdll!RtlEnterCriticalSection` at `0x1800aee9c`
- `ntdll!RtlEnterCriticalSection` at `0x1800aec0f`
- `ntdll!RtlEnterCriticalSection` at `0x1800aed42`
- `ntdll!RtlEnterCriticalSection` at `0x1800aee9c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800aec33`
- `ntdll!RtlLeaveCriticalSection` at `0x1800aedd9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800aefbe`
- `ntdll!RtlLeaveCriticalSection` at `0x1800aec33`
- `ntdll!RtlLeaveCriticalSection` at `0x1800aedd9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800aefbe`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800aefc8`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800aefd2`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800aefc8`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800aefd2`

## string_xrefs

- `0x1800aef04`: `GMSA account %wZ\%wZ in logon session %x:%#x has gmsa filetime updated from %#I64x to %#I64x, update current: %d, update old: %d\n, refresh: %d`

## pseudocode

```c

```
