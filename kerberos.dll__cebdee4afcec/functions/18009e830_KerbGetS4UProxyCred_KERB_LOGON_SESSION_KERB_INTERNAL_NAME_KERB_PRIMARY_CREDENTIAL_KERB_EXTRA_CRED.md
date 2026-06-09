# KerbGetS4UProxyCred(_KERB_LOGON_SESSION *,_KERB_INTERNAL_NAME *,_KERB_PRIMARY_CREDENTIAL * *,_KERB_EXTRA_CRED * *)

- ea: `0x18009e830`
- end: `0x18009ea5a`
- name: `?KerbGetS4UProxyCred@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_INTERNAL_NAME@@PEAPEAU_KERB_PRIMARY_CREDENTIAL@@PEAPEAU_KERB_EXTRA_CRED@@@Z`
- size: `554`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *, struct _KERB_INTERNAL_NAME *, struct _KERB_PRIMARY_CREDENTIAL **, struct _KERB_EXTRA_CRED **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800566a8`

## callees

- `0x1800068d0`
- `0x180010e90`
- `0x1800163a0`
- `0x18008a304`
- `0x18008b70c`
- `0x18009e830`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18009e956`
- `ntdll!RtlEqualUnicodeString` at `0x18009e956`
- `ntdll!RtlEnterCriticalSection` at `0x18009e863`
- `ntdll!RtlEnterCriticalSection` at `0x18009e883`
- `ntdll!RtlEnterCriticalSection` at `0x18009e863`
- `ntdll!RtlEnterCriticalSection` at `0x18009e883`
- `ntdll!RtlLeaveCriticalSection` at `0x18009ea30`
- `ntdll!RtlLeaveCriticalSection` at `0x18009ea3a`
- `ntdll!RtlLeaveCriticalSection` at `0x18009ea30`
- `ntdll!RtlLeaveCriticalSection` at `0x18009ea3a`

## string_xrefs

- `0x18009e9f7`: `Attempting S4U2Proxy: caller credential %wZ@%wZ\n`

## pseudocode

```c

```
