# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x1800ae644`
- end: `0x1800ae87c`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `568`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004c430`
- `0x18007f720`

## callees

- `0x1800061ba`
- `0x18000ff24`
- `0x18001eeb8`
- `0x1800a1ad0`
- `0x1800ae3a0`
- `0x1800ae644`
- `0x1800ae884`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae6a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae6a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ae673`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ae673`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ae690`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ae690`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae6dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae6dc`
- `ntdll!RtlFreeHeap` at `0x1800ae7fe`
- `ntdll!RtlFreeHeap` at `0x1800ae830`
- `ntdll!RtlFreeHeap` at `0x1800ae85d`
- `ntdll!RtlFreeHeap` at `0x1800ae7fe`
- `ntdll!RtlFreeHeap` at `0x1800ae830`
- `ntdll!RtlFreeHeap` at `0x1800ae85d`

## pseudocode

```c

```
