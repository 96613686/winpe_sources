# RegLoadKeyA

- ea: `0x1800fc320`
- end: `0x1800fc4c6`
- name: `RegLoadKeyA`
- size: `422`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCSTR lpSubKey, LPCSTR lpFile)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x18005bb80`
- `0x18005d0a0`
- `0x1800fc320`
- `0x1800fc5f8`
- `0x18012d578`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800fc409`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800fc409`
- `ntdll!RtlFreeUnicodeString` at `0x1800fc41a`
- `ntdll!RtlFreeUnicodeString` at `0x1800fc48b`
- `ntdll!RtlFreeUnicodeString` at `0x1800fc41a`
- `ntdll!RtlFreeUnicodeString` at `0x1800fc48b`
- `ntdll!RtlNtStatusToDosError` at `0x1800fc3b6`
- `ntdll!RtlNtStatusToDosError` at `0x1800fc3b6`
- `ntdll!RtlInitAnsiStringEx` at `0x1800fc3f0`
- `ntdll!RtlInitAnsiStringEx` at `0x1800fc3f0`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x1800fc3a7`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x1800fc3a7`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegLoadKey` at `0x1800fc472`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegLoadKey` at `0x1800fc472`

## pseudocode

```c

```
