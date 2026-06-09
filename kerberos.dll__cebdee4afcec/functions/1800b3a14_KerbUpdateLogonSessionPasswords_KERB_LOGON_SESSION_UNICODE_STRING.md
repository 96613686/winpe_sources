# KerbUpdateLogonSessionPasswords(_KERB_LOGON_SESSION *,_UNICODE_STRING *)

- ea: `0x1800b3a14`
- end: `0x1800b3b9d`
- name: `?KerbUpdateLogonSessionPasswords@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_UNICODE_STRING@@@Z`
- size: `393`
- prototype: `__int64 __fastcall(struct _KERB_LOGON_SESSION *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800b28c8`

## callees

- `0x180009afc`
- `0x18000a630`
- `0x18007108c`
- `0x18008e4f4`
- `0x1800b3a14`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x1800b3aa6`
- `ntdll!RtlEqualUnicodeString` at `0x1800b3ac5`
- `ntdll!RtlEqualUnicodeString` at `0x1800b3aa6`
- `ntdll!RtlEqualUnicodeString` at `0x1800b3ac5`
- `ntdll!RtlEnterCriticalSection` at `0x1800b3a88`
- `ntdll!RtlEnterCriticalSection` at `0x1800b3a95`
- `ntdll!RtlEnterCriticalSection` at `0x1800b3a88`
- `ntdll!RtlEnterCriticalSection` at `0x1800b3a95`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b3ad6`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b3b4b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b3b70`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b3b79`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b3ad6`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b3b4b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b3b70`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b3b79`

## pseudocode

```c

```
