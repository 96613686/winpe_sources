# VerifyCredentials(ushort *,ushort *,ushort *)

- ea: `0x180038094`
- end: `0x18003822c`
- name: `?VerifyCredentials@@YAKPEAG00@Z`
- size: `408`
- prototype: `unsigned int __fastcall(LPCWSTR lpString, LPCWSTR, LPCWSTR)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180038a00`

## callees

- `0x180007f10`
- `0x18001e1b4`
- `0x180038094`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800380fa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18003810f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180038124`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800380fa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18003810f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180038124`
- `ntdll!RtlNtStatusToDosError` at `0x1800381b6`
- `ntdll!RtlNtStatusToDosError` at `0x1800381d5`
- `ntdll!RtlNtStatusToDosError` at `0x1800381b6`
- `ntdll!RtlNtStatusToDosError` at `0x1800381d5`
- `ntdll!RtlInitUnicodeString` at `0x1800380eb`
- `ntdll!RtlInitUnicodeString` at `0x1800380eb`

## string_xrefs

- `0x1800381e7`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`

## pseudocode

```c

```
