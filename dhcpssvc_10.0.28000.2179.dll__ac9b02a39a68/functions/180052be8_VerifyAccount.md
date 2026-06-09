# VerifyAccount

- ea: `0x180052be8`
- end: `0x180052ca4`
- name: `VerifyAccount`
- size: `188`
- prototype: `__int64 __fastcall(LPCWSTR lpszUsername, LPCWSTR lpszDomain, LPCWSTR lpszPassword)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18005284c`

## callees

- `0x180052be8`

## import_xrefs

- `ADVAPI32!LogonUserW` at `0x180052c3b`
- `ADVAPI32!LogonUserW` at `0x180052c3b`
- `RPCRT4!RpcImpersonateClient` at `0x180052c0f`
- `RPCRT4!RpcImpersonateClient` at `0x180052c0f`
- `RPCRT4!RpcRevertToSelf` at `0x180052c61`
- `RPCRT4!RpcRevertToSelf` at `0x180052c61`
- `KERNEL32!GetLastError` at `0x180052c4b`
- `KERNEL32!GetLastError` at `0x180052c4b`
- `KERNEL32!CloseHandle` at `0x180052c80`
- `KERNEL32!CloseHandle` at `0x180052c80`

## pseudocode

```c

```
