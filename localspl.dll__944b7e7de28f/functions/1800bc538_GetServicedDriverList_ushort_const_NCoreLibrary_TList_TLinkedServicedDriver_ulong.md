# GetServicedDriverList(ushort const *,NCoreLibrary::TList<TLinkedServicedDriver> *,ulong *)

- ea: `0x1800bc538`
- end: `0x1800bc9b9`
- name: `?GetServicedDriverList@@YAJPEBGPEAV?$TList@VTLinkedServicedDriver@@@NCoreLibrary@@PEAK@Z`
- size: `1153`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x1800bbc74`
- `0x1800bd298`
- `0x1800bd3fc`

## callees

- `0x180015418`
- `0x18001776c`
- `0x18002ff50`
- `0x18003e984`
- `0x1800401a8`
- `0x180046a5c`
- `0x180054638`
- `0x1800bb648`
- `0x1800bc00c`
- `0x1800bc538`
- `0x1800c07bc`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc79c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc7fb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc843`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc79c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc7fb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc843`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800bc5f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800bc5f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bc996`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bc996`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bc5a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bc5a0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800bc699`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800bc699`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bc6e4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bc6e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc89e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc935`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc943`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc951`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc982`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc89e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc935`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc943`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc951`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc982`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bc621`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bc621`

## string_xrefs

- `0x1800bc705`: `INF Path`
- `0x1800bc7db`: `Failed to copy files from ntprint package to `
- `0x1800bc7a9`: `A core v4 package has been serviced: '%ws'`
- `0x1800bc850`: `A core v4 package has been serviced: '%ws'`
- `0x1800bc7b0`: `GetServicedDriverList`
- `0x1800bc7e2`: `GetServicedDriverList`
- `0x1800bc857`: `GetServicedDriverList`

## pseudocode

```c

```
