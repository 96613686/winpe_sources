# PcaUtilityLaunchProcess(ulong *,ushort const *,int)

- ea: `0x1800ee280`
- end: `0x1800ee3d5`
- name: `?PcaUtilityLaunchProcess@@YAKPEAKPEBGH@Z`
- size: `341`
- prototype: `__int64 __fastcall(unsigned int *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180038880`
- `0x1800929c0`

## callees

- `0x180012920`
- `0x18007a9cf`
- `0x1800ee280`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800ee31b`
- `msvcrt!wcscpy_s` at `0x1800ee31b`
- `ntdll!RtlFreeHeap` at `0x1800ee3b5`
- `ntdll!RtlFreeHeap` at `0x1800ee3b5`
- `ntdll!RtlAllocateHeap` at `0x1800ee2e3`
- `ntdll!RtlAllocateHeap` at `0x1800ee2e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee35e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee35e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800ee354`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800ee354`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee38f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee39a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee38f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee39a`

## string_xrefs

- `0x1800ee364`: `CreateProcess failed [%d]`

## pseudocode

```c

```
