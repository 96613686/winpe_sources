# GetDot3ServiceRootRegistryLocation(ulong,ushort *)

- ea: `0x18001bffc`
- end: `0x18001c07a`
- name: `?GetDot3ServiceRootRegistryLocation@@YAKKPEAG@Z`
- size: `126`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001c080`
- `0x18001c780`
- `0x18001dff0`
- `0x18001e620`

## callees

- `0x18000a9c0`
- `0x18001bffc`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18001c029`
- `ntdll!RtlGetPersistedStateLocation` at `0x18001c029`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c033`

## pseudocode

```c

```
