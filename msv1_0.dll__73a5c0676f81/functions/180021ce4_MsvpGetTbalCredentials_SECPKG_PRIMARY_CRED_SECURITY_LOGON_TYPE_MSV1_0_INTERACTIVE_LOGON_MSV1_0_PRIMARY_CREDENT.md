# MsvpGetTbalCredentials(_SECPKG_PRIMARY_CRED *,_SECURITY_LOGON_TYPE,_MSV1_0_INTERACTIVE_LOGON *,_MSV1_0_PRIMARY_CREDENTIAL * *,ulong *)

- ea: `0x180021ce4`
- end: `0x180021df4`
- name: `?MsvpGetTbalCredentials@@YAJPEAU_SECPKG_PRIMARY_CRED@@W4_SECURITY_LOGON_TYPE@@PEAU_MSV1_0_INTERACTIVE_LOGON@@PEAPEAU_MSV1_0_PRIMARY_CREDENTIAL@@PEAK@Z`
- size: `272`
- prototype: `__int64 __fastcall(struct _SECPKG_PRIMARY_CRED *, enum _SECURITY_LOGON_TYPE, struct _MSV1_0_INTERACTIVE_LOGON *, struct _MSV1_0_PRIMARY_CREDENTIAL **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a470`

## callees

- `0x180021ce4`
- `0x180055abc`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180021d30`
- `ntdll!RtlEqualUnicodeString` at `0x180021d85`
- `ntdll!RtlEqualUnicodeString` at `0x180021d99`
- `ntdll!RtlEqualUnicodeString` at `0x180021d30`
- `ntdll!RtlEqualUnicodeString` at `0x180021d85`
- `ntdll!RtlEqualUnicodeString` at `0x180021d99`

## pseudocode

```c

```
