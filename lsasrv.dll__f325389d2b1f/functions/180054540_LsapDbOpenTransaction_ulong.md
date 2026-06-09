# LsapDbOpenTransaction(ulong)

- ea: `0x180054540`
- end: `0x18005482f`
- name: `?LsapDbOpenTransaction@@YAJK@Z`
- size: `751`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18010c0e0`

## callees

- `0x180054540`
- `0x180054838`
- `0x1800b86d0`
- `0x1800b9304`
- `0x18011f3a8`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005460d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005460d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005474c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005474c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005472a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005472a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800545e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800546f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800545e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800546f3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800546bc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800546bc`
- `ntdll!RtlAllocateHeap` at `0x180054779`
- `ntdll!RtlAllocateHeap` at `0x180054779`
- `ntdll!RtlLeaveCriticalSection` at `0x1800546d9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800546d9`
- `ntdll!RtlEnterCriticalSection` at `0x18005466f`
- `ntdll!RtlEnterCriticalSection` at `0x18005466f`

## string_xrefs

- `0x1800546b0`: `SYSTEM\CurrentControlSet\Services\NTDS`
- `0x180054742`: `InitializeLsaDbExtension`

## pseudocode

```c

```
