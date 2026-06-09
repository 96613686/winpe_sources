# CTSSession::TerminateSession(CConvertibleLock &)

- ea: `0x18001228c`
- end: `0x18001233a`
- name: `?TerminateSession@CTSSession@@AEAAJAEAVCConvertibleLock@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(CTSSession *__hidden this, struct CConvertibleLock *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180010f50`

## callees

- `0x18001228c`
- `0x180012e04`
- `0x1800489b0`
- `0x180072b94`

## import_xrefs

- `ntdll!RtlConvertSharedToExclusive` at `0x1800122f1`
- `ntdll!RtlConvertSharedToExclusive` at `0x1800122f1`
- `ntdll!RtlConvertExclusiveToShared` at `0x1800122da`
- `ntdll!RtlConvertExclusiveToShared` at `0x1800122da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012317`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012317`
- `KERNELBASE!WTSGetServiceSessionId` at `0x1800122c7`
- `KERNELBASE!WTSGetServiceSessionId` at `0x1800122c7`

## pseudocode

```c

```
