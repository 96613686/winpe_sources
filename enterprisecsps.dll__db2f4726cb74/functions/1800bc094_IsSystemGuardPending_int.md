# IsSystemGuardPending(int *)

- ea: `0x1800bc094`
- end: `0x1800bc22b`
- name: `?IsSystemGuardPending@@YAJPEAH@Z`
- size: `407`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800babdc`

## callees

- `0x180008de0`
- `0x18000d4d4`
- `0x180025ac0`
- `0x18002dcc8`
- `0x1800bc094`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x1800bc1c8`
- `ntdll!NtQuerySystemInformation` at `0x1800bc1c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bc15c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bc15c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bc0f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bc0f5`

## pseudocode

```c

```
