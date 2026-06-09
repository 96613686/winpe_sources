# URL_AUTHZ_RULE_ENTRY::ResolveUserNameToSidForWindowsPrincipal(STRU *,BUFFER *)

- ea: `0x180024d44`
- end: `0x180024f34`
- name: `?ResolveUserNameToSidForWindowsPrincipal@URL_AUTHZ_RULE_ENTRY@@CAJPEAVSTRU@@PEAVBUFFER@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(struct STRU *, struct BUFFER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024174`

## callees

- `0x180024d44`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180024df1`
- `KERNEL32!GetLastError` at `0x180024dfc`
- `KERNEL32!GetLastError` at `0x180024e3a`
- `KERNEL32!GetLastError` at `0x180024ea4`
- `KERNEL32!GetLastError` at `0x180024df1`
- `KERNEL32!GetLastError` at `0x180024dfc`
- `KERNEL32!GetLastError` at `0x180024e3a`
- `KERNEL32!GetLastError` at `0x180024ea4`
- `ADVAPI32!LookupAccountNameW` at `0x180024de3`
- `ADVAPI32!LookupAccountNameW` at `0x180024e9a`
- `ADVAPI32!LookupAccountNameW` at `0x180024de3`
- `ADVAPI32!LookupAccountNameW` at `0x180024e9a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180024f0d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180024f0d`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180024e30`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180024e63`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180024e30`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180024e63`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180024da1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180024da1`
- `iisutil!PuDbgPrintError` at `0x180024ef6`
- `iisutil!PuDbgPrintError` at `0x180024ef6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180024f02`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180024f02`

## string_xrefs

- `0x180024ee1`: `URL_AUTHZ_RULE_ENTRY::ResolveUserNameToSidForWindowsPrincipal`

## pseudocode

```c

```
