# LsaDbExtIsHandleDsHandle(_LSAP_DB_HANDLE *)

- ea: `0x18001f530`
- end: `0x18001f7c0`
- name: `?LsaDbExtIsHandleDsHandle@@YAEPEAU_LSAP_DB_HANDLE@@@Z`
- size: `656`
- prototype: `unsigned __int8 __fastcall(struct _LSAP_DB_HANDLE *)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001efd0`
- `0x180052990`
- `0x180053558`
- `0x1800a0590`
- `0x18010c0e0`
- `0x18010c5f0`
- `0x18010c870`

## callees

- `0x18001f530`
- `0x1800b86d0`
- `0x1800b9304`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f5e2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f5e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f704`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f704`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f6e2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f6e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f5be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f6ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f5be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f6ae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f676`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f676`
- `ntdll!RtlAllocateHeap` at `0x18001f731`
- `ntdll!RtlAllocateHeap` at `0x18001f731`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f694`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f694`
- `ntdll!RtlEnterCriticalSection` at `0x18001f629`
- `ntdll!RtlEnterCriticalSection` at `0x18001f629`

## string_xrefs

- `0x18001f66a`: `SYSTEM\CurrentControlSet\Services\NTDS`
- `0x18001f6fa`: `InitializeLsaDbExtension`

## pseudocode

```c

```
