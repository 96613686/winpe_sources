# CReflectedDump::GetReflectionObjectForPid(ulong,utl::unique_ptr<IReflectedDump,utl::default_delete<IReflectedDump>> *)

- ea: `0x18004752c`
- end: `0x18004784b`
- name: `?GetReflectionObjectForPid@CReflectedDump@@SAJKPEAV?$unique_ptr@VIReflectedDump@@U?$default_delete@VIReflectedDump@@@utl@@@utl@@@Z`
- size: `799`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x180047990`

## callees

- `0x1800028b4`
- `0x1800028ec`
- `0x180003474`
- `0x180004c92`
- `0x180009ed8`
- `0x180009f00`
- `0x180046b14`
- `0x18004752c`
- `0x1800478e4`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047607`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800475a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800475a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047728`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800477f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800477f7`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180047615`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18004762b`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180047615`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18004762b`

## pseudocode

```c

```
