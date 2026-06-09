# LogonTaskBlackBox::Initialize<70>(LOGON_TASK_DEFINITION const *,LogonTypeFlags)

- ea: `0x140093ddc`
- end: `0x140093ed7`
- name: `??$Initialize@$0EG@@LogonTaskBlackBox@@QEAAJPEBULOGON_TASK_DEFINITION@@W4LogonTypeFlags@@@Z`
- size: `251`
- prototype: `__int64 __fastcall(LogonTaskBlackBox *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x14001021c`

## callees

- `0x14001f500`
- `0x140072988`
- `0x140093ddc`
- `0x1400954e0`
- `0x140104ce0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140093e3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140093e3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140093e9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140093e9a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140093e0f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140093e0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140093e48`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140093e48`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140093e4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140093e4e`

## string_xrefs

- `0x140093ebb`: `shell\lib\logontasks\BlackBoxData.h`

## pseudocode

```c

```
