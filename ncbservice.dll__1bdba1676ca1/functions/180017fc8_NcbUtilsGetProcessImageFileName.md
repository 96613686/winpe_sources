# NcbUtilsGetProcessImageFileName

- ea: `0x180017fc8`
- end: `0x18001817a`
- name: `NcbUtilsGetProcessImageFileName`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180004a30`

## callees

- `0x1800050d0`
- `0x18000a0a0`
- `0x180012900`
- `0x180012aa0`
- `0x180017fc8`
- `0x18001d8e0`
- `0x18001e368`

## import_xrefs

- `ntdll!RtlQueryPackageIdentity` at `0x180018073`
- `ntdll!RtlQueryPackageIdentity` at `0x180018073`
- `ntdll!RtlNtStatusToDosError` at `0x1800180a2`
- `ntdll!RtlNtStatusToDosError` at `0x1800180c7`
- `ntdll!RtlNtStatusToDosError` at `0x1800180a2`
- `ntdll!RtlNtStatusToDosError` at `0x1800180c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018123`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018123`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800180ed`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800180ed`

## string_xrefs

- `0x1800180a8`: `NcbUtilsGetProcessImageFileName: NcbUtilsAllocCopyString failed`

## pseudocode

```c

```
