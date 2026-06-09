# VerifyAccount

- ea: `0x180052ec0`
- end: `0x180052f79`
- name: `VerifyAccount`
- size: `185`
- prototype: `__int64 __fastcall(LPCWSTR lpszUsername, LPCWSTR lpszDomain, LPCWSTR lpszPassword)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180052b38`

## callees

- `0x180052ec0`

## import_xrefs

- `ADVAPI32!LogonUserW` at `0x180052f10`
- `ADVAPI32!LogonUserW` at `0x180052f10`
- `RPCRT4!RpcImpersonateClient` at `0x180052ee4`
- `RPCRT4!RpcImpersonateClient` at `0x180052ee4`
- `RPCRT4!RpcRevertToSelf` at `0x180052f36`
- `RPCRT4!RpcRevertToSelf` at `0x180052f36`
- `KERNEL32!GetLastError` at `0x180052f20`
- `KERNEL32!GetLastError` at `0x180052f20`
- `KERNEL32!CloseHandle` at `0x180052f55`
- `KERNEL32!CloseHandle` at `0x180052f55`

## pseudocode

```c

```
