# CGroupPolicySession::WaitForGroupPolicySessionThreadsToTerminate(void)

- ea: `0x180009f60`
- end: `0x18000a3fe`
- name: `?WaitForGroupPolicySessionThreadsToTerminate@CGroupPolicySession@@QEAAXXZ`
- size: `1182`
- prototype: `void __fastcall(CGroupPolicySession *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009d2c`
- `0x18000c398`
- `0x18008b168`
- `0x18008b310`

## callees

- `0x180009f60`
- `0x18004df78`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009fbc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a025`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a0b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009fbc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a025`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a0b5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a17e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a17e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000a322`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000a322`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009fe4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009fe4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a04c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a061`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a133`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a1c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a04c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a061`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a133`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a1c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a257`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a257`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a379`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a037`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a037`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a0da`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a0da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a124`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a124`

## string_xrefs

- `0x18000a1f8`: `WaitForGroupPolicySessionThreadsToTerminate() checked.`
- `0x18000a228`: `WaitForGroupPolicySessionThreadsToTerminate() checked.`
- `0x18000a2b9`: `WaitForGroupPolicySessionThreadsToTerminate() WaitForSingleObject released.`
- `0x18000a2ee`: `WaitForGroupPolicySessionThreadsToTerminate() WaitForSingleObject released.`
- `0x18000a3a8`: `WaitForGroupPolicySessionThreadsToTerminate() WaitForMultipleObjectsEx released.`
- `0x18000a3d2`: `WaitForGroupPolicySessionThreadsToTerminate() WaitForMultipleObjectsEx released.`

## pseudocode

```c

```
