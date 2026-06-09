# appIsolation::IsolationEvents::FwMoneisRegistrationApiShutdown(void)

- ea: `0x1800c26a0`
- end: `0x1800c27cb`
- name: `?FwMoneisRegistrationApiShutdown@IsolationEvents@appIsolation@@QEAAXXZ`
- size: `299`
- prototype: `void __fastcall(appIsolation::IsolationEvents *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800bf660`
- `0x1800c25c0`

## callees

- `0x1800089bc`
- `0x1800192e0`
- `0x18006a710`
- `0x18006a964`
- `0x1800c26a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c273e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c273e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c26fb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c26fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c2762`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800c2762`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c2713`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c2713`
- `fwbase!FwCriticalSectionDestroy` at `0x1800c277e`
- `fwbase!FwCriticalSectionDestroy` at `0x1800c277e`

## string_xrefs

- `0x1800c2729`: `mpssvc.dll`
- `0x1800c274d`: `mpssvc.dll`

## pseudocode

```c

```
