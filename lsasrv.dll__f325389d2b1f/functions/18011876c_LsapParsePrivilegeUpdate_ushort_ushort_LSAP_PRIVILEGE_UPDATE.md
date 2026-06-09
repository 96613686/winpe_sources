# LsapParsePrivilegeUpdate(ushort *,ushort *,LSAP_PRIVILEGE_UPDATE *)

- ea: `0x18011876c`
- end: `0x180118aac`
- name: `?LsapParsePrivilegeUpdate@@YAJPEAG0PEAULSAP_PRIVILEGE_UPDATE@@@Z`
- size: `832`
- prototype: `__int64 __fastcall(RPC_WSTR StringUuid, wchar_t *Str, struct LSAP_PRIVILEGE_UPDATE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801190f8`

## callees

- `0x180071c60`
- `0x180097c3c`
- `0x18009829c`
- `0x1800ada18`
- `0x1800b86d0`
- `0x18011876c`
- `0x18011944c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801188d3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801188d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180118a06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180118a5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180118a06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180118a5b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18011894f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18011894f`
- `ntdll!wcsstr` at `0x180118846`
- `ntdll!wcsstr` at `0x180118894`
- `ntdll!wcsstr` at `0x180118846`
- `ntdll!wcsstr` at `0x180118894`
- `ntdll!RtlEqualUnicodeString` at `0x1801189c5`
- `ntdll!RtlEqualUnicodeString` at `0x1801189c5`
- `ntdll!RtlInitUnicodeString` at `0x18011898b`
- `ntdll!RtlInitUnicodeString` at `0x18011898b`
- `RPCRT4!UuidFromStringW` at `0x1801187f8`
- `RPCRT4!UuidFromStringW` at `0x1801187f8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180118908`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180118908`

## string_xrefs

- `0x1801188c5`: `PrivilegeAdd`

## pseudocode

```c

```
