# CredpReadCredentialFromFile(ushort const *,ushort const *,ProtectionMethodType,uchar *,ulong,ushort const * *,ulong,_CANONICAL_CREDENTIAL * *,long *)

- ea: `0x180098b70`
- end: `0x180099496`
- name: `?CredpReadCredentialFromFile@@YAJPEBG0W4ProtectionMethodType@@PEAEKPEAPEBGKPEAPEAU_CANONICAL_CREDENTIAL@@PEAJ@Z`
- size: `2342`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, __int64, __int64, __int64, __int64, char, _QWORD *, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting`

## callers

- `0x1800994a0`

## callees

- `0x18000124c`
- `0x180009120`
- `0x180011278`
- `0x180016f70`
- `0x1800284d4`
- `0x18003a880`
- `0x180077ffc`
- `0x180097f74`
- `0x18009829c`
- `0x180098b70`
- `0x1800b86d0`
- `0x1800c4064`
- `0x1800c7258`
- `0x1800c7bdc`
- `0x1800c7cb8`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098d20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098d4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009926c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098d20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098d4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009926c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800990e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800990e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180099430`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180099430`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800993d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800993d3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180098ceb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180098ceb`
- `ntdll!RtlFreeHeap` at `0x1800993c5`
- `ntdll!RtlFreeHeap` at `0x18009941c`
- `ntdll!RtlFreeHeap` at `0x180099462`
- `ntdll!RtlFreeHeap` at `0x1800993c5`
- `ntdll!RtlFreeHeap` at `0x18009941c`
- `ntdll!RtlFreeHeap` at `0x180099462`

## pseudocode

```c

```
