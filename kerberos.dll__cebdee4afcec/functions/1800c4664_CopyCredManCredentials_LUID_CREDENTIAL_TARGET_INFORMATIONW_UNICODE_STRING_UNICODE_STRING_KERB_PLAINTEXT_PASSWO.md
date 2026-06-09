# CopyCredManCredentials(_LUID *,_CREDENTIAL_TARGET_INFORMATIONW *,_UNICODE_STRING *,_UNICODE_STRING *,_KERB_PLAINTEXT_PASSWORD *)

- ea: `0x1800c4664`
- end: `0x1800c48c6`
- name: `?CopyCredManCredentials@@YAJPEAU_LUID@@PEAU_CREDENTIAL_TARGET_INFORMATIONW@@PEAU_UNICODE_STRING@@2PEAU_KERB_PLAINTEXT_PASSWORD@@@Z`
- size: `610`
- prototype: `__int64 __usercall@<rax>(struct _LUID *@<rcx>, struct _CREDENTIAL_TARGET_INFORMATIONW *@<rdx>, struct _UNICODE_STRING *@<r8>, struct _UNICODE_STRING *@<r9>, struct _KERB_PLAINTEXT_PASSWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180063e44`

## callees

- `0x1800068d0`
- `0x180008e18`
- `0x180009afc`
- `0x18000a630`
- `0x18000b300`
- `0x180014b40`
- `0x180063c80`
- `0x18008ab80`
- `0x1800c4664`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800c469a`
- `ntdll!RtlInitUnicodeString` at `0x1800c46a5`
- `ntdll!RtlInitUnicodeString` at `0x1800c469a`
- `ntdll!RtlInitUnicodeString` at `0x1800c46a5`
- `ntdll!RtlEnterCriticalSection` at `0x1800c478b`
- `ntdll!RtlEnterCriticalSection` at `0x1800c478b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800c47b0`
- `ntdll!RtlLeaveCriticalSection` at `0x1800c47b0`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x1800c4755`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x1800c4755`

## pseudocode

```c

```
