# _anonymous_namespace_::GetSidFromCurrentProcessToken

- ea: `0x180142a74`
- end: `0x180142b30`
- name: `_anonymous_namespace_::GetSidFromCurrentProcessToken`
- size: `188`
- prototype: `__int64 __usercall@<rax>(TOKEN_INFORMATION_CLASS TokenInformationClass@<ecx>, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180142c04`

## callees

- `0x1800e795c`
- `0x180142a74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180142ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180142ad4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180142aa9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180142aa9`

## pseudocode

```c

```
