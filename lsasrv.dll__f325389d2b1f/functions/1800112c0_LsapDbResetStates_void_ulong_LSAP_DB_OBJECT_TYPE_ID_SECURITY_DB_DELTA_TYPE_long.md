# LsapDbResetStates(void *,ulong,_LSAP_DB_OBJECT_TYPE_ID,_SECURITY_DB_DELTA_TYPE,long)

- ea: `0x1800112c0`
- end: `0x1800117dc`
- name: `?LsapDbResetStates@@YAJPEAXKW4_LSAP_DB_OBJECT_TYPE_ID@@W4_SECURITY_DB_DELTA_TYPE@@J@Z`
- size: `1308`
- prototype: `int __high(void *, unsigned int, enum _LSAP_DB_OBJECT_TYPE_ID, enum _SECURITY_DB_DELTA_TYPE, int)`
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ddc0`
- `0x18000f8f0`
- `0x1800101e0`
- `0x18010c0e0`

## callees

- `0x180011278`
- `0x1800112c0`
- `0x180021e14`
- `0x1800284d4`
- `0x18008af08`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800b9304`
- `0x18011f3a8`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800113d0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800113d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800115b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800115b4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180011592`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180011592`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800113ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800114b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800113ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800114b8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011531`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011531`
- `ntdll!RtlAllocateHeap` at `0x1800115e1`
- `ntdll!RtlAllocateHeap` at `0x1800115e1`
- `ntdll!RtlReleaseResource` at `0x180011684`
- `ntdll!RtlReleaseResource` at `0x18001175d`
- `ntdll!RtlReleaseResource` at `0x18001177c`
- `ntdll!RtlReleaseResource` at `0x180011684`
- `ntdll!RtlReleaseResource` at `0x18001175d`
- `ntdll!RtlReleaseResource` at `0x18001177c`
- `ntdll!RtlLeaveCriticalSection` at `0x18001142d`
- `ntdll!RtlLeaveCriticalSection` at `0x18001154e`
- `ntdll!RtlLeaveCriticalSection` at `0x180011671`
- `ntdll!RtlLeaveCriticalSection` at `0x180011697`
- `ntdll!RtlLeaveCriticalSection` at `0x18001171d`
- `ntdll!RtlLeaveCriticalSection` at `0x18001142d`
- `ntdll!RtlLeaveCriticalSection` at `0x18001154e`
- `ntdll!RtlLeaveCriticalSection` at `0x180011671`
- `ntdll!RtlLeaveCriticalSection` at `0x180011697`
- `ntdll!RtlLeaveCriticalSection` at `0x18001171d`
- `ntdll!RtlEnterCriticalSection` at `0x1800114e4`
- `ntdll!RtlEnterCriticalSection` at `0x1800114e4`

## string_xrefs

- `0x180011525`: `SYSTEM\CurrentControlSet\Services\NTDS`
- `0x1800115aa`: `InitializeLsaDbExtension`

## pseudocode

```c

```
