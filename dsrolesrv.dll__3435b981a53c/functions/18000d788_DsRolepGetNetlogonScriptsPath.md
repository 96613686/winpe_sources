# DsRolepGetNetlogonScriptsPath

- ea: `0x18000d788`
- end: `0x18000d8f4`
- name: `DsRolepGetNetlogonScriptsPath`
- size: `364`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c228`
- `0x18000da70`

## callees

- `0x18000d788`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d7cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d823`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d7cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d823`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d854`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d854`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8a5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000d846`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000d897`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000d846`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000d897`
- `ntdll!RtlAllocateHeap` at `0x18000d7f0`
- `ntdll!RtlAllocateHeap` at `0x18000d877`
- `ntdll!RtlAllocateHeap` at `0x18000d7f0`
- `ntdll!RtlAllocateHeap` at `0x18000d877`
- `ntdll!RtlFreeHeap` at `0x18000d8bf`
- `ntdll!RtlFreeHeap` at `0x18000d8d9`
- `ntdll!RtlFreeHeap` at `0x18000d8bf`
- `ntdll!RtlFreeHeap` at `0x18000d8d9`

## pseudocode

```c

```
