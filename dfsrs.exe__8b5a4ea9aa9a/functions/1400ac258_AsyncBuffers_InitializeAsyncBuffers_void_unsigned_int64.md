# AsyncBuffers::InitializeAsyncBuffers(void *,unsigned __int64)

- ea: `0x1400ac258`
- end: `0x1400ac56d`
- name: `?InitializeAsyncBuffers@AsyncBuffers@@IEAAPEAVFrsStatus@@PEAX_K@Z`
- size: `789`
- prototype: `struct FrsStatus *__fastcall(AsyncBuffers *__hidden this, HANDLE FileHandle, unsigned __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1400ad380`
- `0x1400ad968`
- `0x1400ae220`

## callees

- `0x1400046cc`
- `0x14000cdc0`
- `0x14000e34c`
- `0x1400ac258`
- `0x1400ac574`
- `0x1400ad8ac`
- `0x1401af7b0`
- `0x1401b9494`
- `0x1401bda10`

## import_xrefs

- `KERNEL32!VirtualAlloc` at `0x1400ac3a5`
- `KERNEL32!VirtualAlloc` at `0x1400ac3a5`
- `KERNEL32!GetLastError` at `0x1400ac3d7`
- `KERNEL32!GetLastError` at `0x1400ac3d7`
- `KERNEL32!GetCurrentThreadId` at `0x1400ac3c9`
- `KERNEL32!GetCurrentThreadId` at `0x1400ac452`
- `KERNEL32!GetCurrentThreadId` at `0x1400ac514`
- `KERNEL32!GetCurrentThreadId` at `0x1400ac3c9`
- `KERNEL32!GetCurrentThreadId` at `0x1400ac452`
- `KERNEL32!GetCurrentThreadId` at `0x1400ac514`
- `ntdll!RtlNtStatusToDosError` at `0x1400ac462`
- `ntdll!RtlNtStatusToDosError` at `0x1400ac462`
- `ntdll!NtSetInformationFile` at `0x1400ac444`
- `ntdll!NtSetInformationFile` at `0x1400ac444`

## pseudocode

```c

```
