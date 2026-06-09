# Windows::Isolation::Implementation::Rtl::iso_RegQueryValue(HKEY__ *,Windows::Isolation::Implementation::Rtl::CWin32FullPath const *,ulong *,ulong *,uchar *,ulong *)

- ea: `0x1800262e0`
- end: `0x1800263d4`
- name: `?iso_RegQueryValue@Rtl@Implementation@Isolation@Windows@@YAJPEAUHKEY__@@PEBVCWin32FullPath@1234@PEAK2PEAE2@Z`
- size: `244`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, HKEY@<rdx>, const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *@<r8>, unsigned int *@<r9>, unsigned int *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800254e0`

## callees

- `0x1800262e0`
- `0x1800b8a44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180026366`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180026366`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800263c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800263c5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026332`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026391`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026332`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026391`

## pseudocode

```c

```
