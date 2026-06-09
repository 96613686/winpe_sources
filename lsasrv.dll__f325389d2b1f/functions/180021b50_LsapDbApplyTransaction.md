# LsapDbApplyTransaction

- ea: `0x180021b50`
- end: `0x180021e0d`
- name: `LsapDbApplyTransaction`
- size: `701`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800204c0`
- `0x180021230`
- `0x1801100f0`
- `0x180110410`
- `0x1801108a0`
- `0x18011bfd0`

## callees

- `0x180021b50`
- `0x180021e14`
- `0x1800b86d0`
- `0x1800b9304`
- `0x18011f3a8`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021bfe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021bfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021d2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021d2d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180021d0b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180021d0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021bda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021c59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021bda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021c59`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021ccf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021ccf`
- `ntdll!RtlAllocateHeap` at `0x180021d5a`
- `ntdll!RtlAllocateHeap` at `0x180021d5a`
- `ntdll!RtlLeaveCriticalSection` at `0x180021ced`
- `ntdll!RtlLeaveCriticalSection` at `0x180021ced`
- `ntdll!RtlEnterCriticalSection` at `0x180021c82`
- `ntdll!RtlEnterCriticalSection` at `0x180021c82`

## string_xrefs

- `0x180021cc3`: `SYSTEM\CurrentControlSet\Services\NTDS`
- `0x180021d23`: `InitializeLsaDbExtension`

## pseudocode

```c

```
