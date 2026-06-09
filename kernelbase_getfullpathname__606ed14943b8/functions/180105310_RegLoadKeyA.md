# RegLoadKeyA

- ea: `0x180105310`
- end: `0x1801054e4`
- name: `RegLoadKeyA`
- size: `468`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCSTR lpSubKey, LPCSTR lpFile)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x18005e7e0`
- `0x18005feb0`
- `0x180105310`
- `0x180105638`
- `0x180136e28`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x18010540b`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18010540b`
- `ntdll!RtlFreeUnicodeString` at `0x180105422`
- `ntdll!RtlFreeUnicodeString` at `0x1801054a2`
- `ntdll!RtlFreeUnicodeString` at `0x180105422`
- `ntdll!RtlFreeUnicodeString` at `0x1801054a2`
- `ntdll!RtlNtStatusToDosError` at `0x1801053ac`
- `ntdll!RtlNtStatusToDosError` at `0x1801053ac`
- `ntdll!RtlInitAnsiStringEx` at `0x1801053ec`
- `ntdll!RtlInitAnsiStringEx` at `0x1801053ec`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180105397`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180105397`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegLoadKey` at `0x180105483`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegLoadKey` at `0x180105483`

## pseudocode

```c

```
