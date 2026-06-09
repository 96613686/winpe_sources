# CLogonTaskFramework::_InitializeWinLogonTimeoutWatcher(void)

- ea: `0x140046970`
- end: `0x140046c1d`
- name: `?_InitializeWinLogonTimeoutWatcher@CLogonTaskFramework@@AEAAXXZ`
- size: `685`
- prototype: `void __fastcall(CLogonTaskFramework *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x14004674c`

## callees

- `0x14001b2c8`
- `0x140046970`
- `0x140046c24`
- `0x140047500`
- `0x140047558`
- `0x140047a3c`
- `0x140047dc8`
- `0x140086b94`
- `0x140087664`
- `0x14008daf8`
- `0x14009ac68`
- `0x1400ae6b8`
- `0x14010e160`
- `0x1401d9010`

## import_xrefs

- `ntdll!NtQueryWnfStateData` at `0x140046a01`
- `ntdll!NtQueryWnfStateData` at `0x140046a01`
- `ntdll!RtlPublishWnfStateData` at `0x140046bba`
- `ntdll!RtlPublishWnfStateData` at `0x140046bba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140046aec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140046aec`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140046ac0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140046ac0`

## string_xrefs

- `0x140046bcf`: `shell\lib\logontasks\logontasks.cpp`
- `0x140046aa0`: `LogonTaskProgressMapping`

## pseudocode

```c

```
