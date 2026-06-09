# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x1800ad1ac`
- end: `0x1800ad3c5`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `537`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004a844`
- `0x18007dbfc`

## callees

- `0x18000697a`
- `0x18000e234`
- `0x18001e32c`
- `0x1800ace68`
- `0x1800acef4`
- `0x1800ad1ac`
- `0x1800ad3cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad202`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ad1f2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ad1f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ad1d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ad1d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ad23b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ad23b`
- `ntdll!RtlFreeHeap` at `0x1800ad29a`
- `ntdll!RtlFreeHeap` at `0x1800ad37b`
- `ntdll!RtlFreeHeap` at `0x1800ad3b2`
- `ntdll!RtlFreeHeap` at `0x1800ad29a`
- `ntdll!RtlFreeHeap` at `0x1800ad37b`
- `ntdll!RtlFreeHeap` at `0x1800ad3b2`

## pseudocode

```c

```
