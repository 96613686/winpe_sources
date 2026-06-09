# PuGetRegistryValue(HKEY__ *,ushort *,ushort *,void * *,ulong *)

- ea: `0x1801a459c`
- end: `0x1801a4705`
- name: `?PuGetRegistryValue@@YAHPEAUHKEY__@@PEAG1PEAPEAXPEAK@Z`
- size: `361`
- prototype: `int(HKEY, unsigned __int16 *, unsigned __int16 *, void **, unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1801a0db0`
- `0x1801a3ba4`
- `0x1801a4884`
- `0x1801a5388`
- `0x1801a5fb4`

## callees

- `0x1800298d0`
- `0x1801a459c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a45ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a45ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a4641`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a46d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a4641`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a46d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a4661`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a4661`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a46c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a46c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a45ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a45ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801a462d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801a4699`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801a462d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801a4699`

## pseudocode

```c

```
