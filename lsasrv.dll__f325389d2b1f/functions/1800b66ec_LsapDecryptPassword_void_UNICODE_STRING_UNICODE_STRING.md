# LsapDecryptPassword(void *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x1800b66ec`
- end: `0x1800b6a22`
- name: `?LsapDecryptPassword@@YAJPEAXPEAU_UNICODE_STRING@@1@Z`
- size: `822`
- prototype: `int(void *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180124194`
- `0x180125c28`

## callees

- `0x1800040d0`
- `0x18000c300`
- `0x180011278`
- `0x180016f70`
- `0x18005fecc`
- `0x180060cb0`
- `0x18007f964`
- `0x1800b66ec`
- `0x18012cd8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6863`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800b6901`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800b6901`
- `ntdll!NtSetInformationThread` at `0x1800b6814`
- `ntdll!NtSetInformationThread` at `0x1800b6955`
- `ntdll!NtSetInformationThread` at `0x1800b6814`
- `ntdll!NtSetInformationThread` at `0x1800b6955`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x1800b6781`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x1800b6781`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x1800b684f`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x1800b68ba`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x1800b684f`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x1800b68ba`

## string_xrefs

- `0x1800b6828`: `NtSetInformationThread(Impersonate)`
- `0x1800b696a`: `NtSetInformationThread(Unimpersonate)`

## pseudocode

```c

```
