# CTSSession::TerminateSession(CConvertibleLock &)

- ea: `0x18000a3c8`
- end: `0x18000a45d`
- name: `?TerminateSession@CTSSession@@AEAAJAEAVCConvertibleLock@@@Z`
- size: `149`
- prototype: `__int64 __fastcall(CTSSession *__hidden this, struct CConvertibleLock *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180009f50`

## callees

- `0x18000a3c8`
- `0x18000f260`
- `0x180045998`
- `0x18006ebec`

## import_xrefs

- `ntdll!RtlConvertSharedToExclusive` at `0x18000a421`
- `ntdll!RtlConvertSharedToExclusive` at `0x18000a421`
- `ntdll!RtlConvertExclusiveToShared` at `0x18000a410`
- `ntdll!RtlConvertExclusiveToShared` at `0x18000a410`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a441`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a441`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000a403`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000a403`

## pseudocode

```c

```
