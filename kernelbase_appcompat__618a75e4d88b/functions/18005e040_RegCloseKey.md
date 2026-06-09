# RegCloseKey

- ea: `0x18005e040`
- end: `0x18005e2e3`
- name: `RegCloseKey`
- size: `675`
- prototype: `LSTATUS __stdcall(HKEY hKey)`
- caller_count: `81`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180014b30`
- `0x180019df0`
- `0x18002bf6c`
- `0x18002c150`
- `0x18002c7a0`
- `0x18002d4b0`
- `0x18002e140`
- `0x18002e1cc`
- `0x18002e360`
- `0x18002ebe8`
- `0x180034380`
- `0x1800543b0`
- `0x1800579c0`
- `0x180058240`
- `0x18005b480`
- `0x18005bbc0`
- `0x18005c0f0`
- `0x18005d410`
- `0x18005da60`
- `0x18005e320`
- `0x18005e7e0`
- `0x18005feb0`
- `0x1800693a0`
- `0x1800694a0`
- `0x180069ba8`
- `0x18006b4a8`
- `0x1800883b0`
- `0x180088660`
- `0x18009fa78`
- `0x1800a04b0`
- `0x1800a0b04`
- `0x1800a1190`
- `0x1800a37f0`
- `0x1800a3c00`
- `0x1800a3ef0`
- `0x1800a4384`
- `0x1800a5010`
- `0x1800a5620`
- `0x1800a5af0`
- `0x1800a5d10`
- `0x1800a6540`
- `0x1800a7ad0`
- `0x1800a7fec`
- `0x1800a85ec`
- `0x1800ac600`
- `0x1800acc60`
- `0x1800acf20`
- `0x1800ad890`
- `0x1800ad900`
- `0x1800ae0a0`

## callees

- `0x18005e040`
- `0x180060124`
- `0x1800e77ec`
- `0x180136e28`
- `0x1801a4010`

## import_xrefs

- `ntdll!SbSelectProcedure` at `0x18005e0a4`
- `ntdll!SbSelectProcedure` at `0x18005e0a4`
- `ntdll!RtlEnterCriticalSection` at `0x18005e11a`
- `ntdll!RtlEnterCriticalSection` at `0x18005e11a`
- `ntdll!RtlLeaveCriticalSection` at `0x18005e154`
- `ntdll!RtlLeaveCriticalSection` at `0x18005e154`
- `ntdll!RtlNtStatusToDosError` at `0x18005e2a7`
- `ntdll!RtlNtStatusToDosError` at `0x18005e2a7`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18005e102`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18019b17e`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18005e102`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18019b17e`
- `ntdll!NtClose` at `0x18005e165`
- `ntdll!NtClose` at `0x18005e165`
- `ntdll!NtResetEvent` at `0x18019b1cb`
- `ntdll!NtResetEvent` at `0x18019b1cb`
- `ntdll!NtQueryEvent` at `0x18019b1a3`
- `ntdll!NtQueryEvent` at `0x18019b1a3`
- `ntdll!RtlFreeHeap` at `0x18005e1de`
- `ntdll!RtlFreeHeap` at `0x18005e1de`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegCloseKey` at `0x18005e287`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegCloseKey` at `0x18005e287`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegCloseKey` at `0x18005e2c5`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegCloseKey` at `0x18005e2c5`

## pseudocode

```c

```
