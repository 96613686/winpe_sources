# LsaDbExtIsDsWriteDs(void)

- ea: `0x18001fde0`
- end: `0x18002007b`
- name: `?LsaDbExtIsDsWriteDs@@YAEXZ`
- size: `667`
- prototype: `unsigned __int8(void)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001f7c8`
- `0x18010c0e0`
- `0x18010ddc0`
- `0x18010e1f0`
- `0x1801100f0`
- `0x180110410`
- `0x18011b548`

## callees

- `0x18001fde0`
- `0x1800b86d0`
- `0x1800b9304`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001fe8d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001fe8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ffbf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ffbf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ff9d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ff9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fe69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ff58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fe69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ff58`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ff20`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ff20`
- `ntdll!RtlAllocateHeap` at `0x18001ffec`
- `ntdll!RtlAllocateHeap` at `0x18001ffec`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ff3e`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ff3e`
- `ntdll!RtlEnterCriticalSection` at `0x18001fed3`
- `ntdll!RtlEnterCriticalSection` at `0x18001fed3`

## string_xrefs

- `0x18001ff14`: `SYSTEM\CurrentControlSet\Services\NTDS`
- `0x18001ffb5`: `InitializeLsaDbExtension`

## pseudocode

```c

```
