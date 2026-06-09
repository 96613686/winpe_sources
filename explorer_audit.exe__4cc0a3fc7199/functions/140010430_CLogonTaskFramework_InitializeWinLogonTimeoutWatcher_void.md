# CLogonTaskFramework::_InitializeWinLogonTimeoutWatcher(void)

- ea: `0x140010430`
- end: `0x1400106c4`
- name: `?_InitializeWinLogonTimeoutWatcher@CLogonTaskFramework@@AEAAXXZ`
- size: `660`
- prototype: `void __fastcall(CLogonTaskFramework *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x14001021c`

## callees

- `0x140010430`
- `0x1400106cc`
- `0x140010f54`
- `0x140010fa8`
- `0x140011094`
- `0x1400113e0`
- `0x14001eba8`
- `0x1400811ac`
- `0x14008194c`
- `0x14008840c`
- `0x1400954e0`
- `0x1400a8c88`
- `0x1401040e0`
- `0x1401db010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x140010668`
- `ntdll!RtlPublishWnfStateData` at `0x140010668`
- `ntdll!NtQueryWnfStateData` at `0x1400104c1`
- `ntdll!NtQueryWnfStateData` at `0x1400104c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400105a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400105a0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14001057a`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14001057a`

## string_xrefs

- `0x140010677`: `shell\lib\logontasks\logontasks.cpp`
- `0x14001055a`: `LogonTaskProgressMapping`

## pseudocode

```c

```
