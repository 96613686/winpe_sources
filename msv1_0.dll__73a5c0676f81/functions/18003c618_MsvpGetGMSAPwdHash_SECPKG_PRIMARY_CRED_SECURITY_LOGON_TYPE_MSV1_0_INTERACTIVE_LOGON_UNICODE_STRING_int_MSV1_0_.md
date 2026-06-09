# MsvpGetGMSAPwdHash(_SECPKG_PRIMARY_CRED *,_SECURITY_LOGON_TYPE,_MSV1_0_INTERACTIVE_LOGON *,_UNICODE_STRING *,int *,_MSV1_0_PRIMARY_CREDENTIAL *,_MSV1_0_PRIMARY_CREDENTIAL *)

- ea: `0x18003c618`
- end: `0x18003c8c1`
- name: `?MsvpGetGMSAPwdHash@@YAJPEAU_SECPKG_PRIMARY_CRED@@W4_SECURITY_LOGON_TYPE@@PEAU_MSV1_0_INTERACTIVE_LOGON@@PEAU_UNICODE_STRING@@PEAHPEAU_MSV1_0_PRIMARY_CREDENTIAL@@5@Z`
- size: `681`
- prototype: `__int64 __fastcall(struct _SECPKG_PRIMARY_CRED *, enum _SECURITY_LOGON_TYPE, struct _MSV1_0_INTERACTIVE_LOGON *, struct _UNICODE_STRING *, int *, struct _MSV1_0_PRIMARY_CREDENTIAL *, struct _MSV1_0_PRIMARY_CREDENTIAL *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a470`

## callees

- `0x18002ee7c`
- `0x180030844`
- `0x18003c618`
- `0x18006d010`

## import_xrefs

- `NtlmShared!MsvpPutClearOwfsInPrimaryCredentialNew` at `0x18003c7a7`
- `NtlmShared!MsvpPutClearOwfsInPrimaryCredentialNew` at `0x18003c7ef`
- `NtlmShared!MsvpPutClearOwfsInPrimaryCredentialNew` at `0x18003c7a7`
- `NtlmShared!MsvpPutClearOwfsInPrimaryCredentialNew` at `0x18003c7ef`
- `ntdll!RtlEqualUnicodeString` at `0x18003c694`
- `ntdll!RtlEqualUnicodeString` at `0x18003c694`

## pseudocode

```c

```
