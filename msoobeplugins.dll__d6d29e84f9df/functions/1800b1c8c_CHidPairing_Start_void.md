# CHidPairing::_Start(void)

- ea: `0x1800b1c8c`
- end: `0x1800b20d4`
- name: `?_Start@CHidPairing@@AEAAJXZ`
- size: `1096`
- prototype: `__int64 __fastcall(CHidPairing *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800b2b60`

## callees

- `0x18000ac48`
- `0x180018a04`
- `0x1800b1c8c`
- `0x1800b20dc`
- `0x1800b2254`
- `0x1800b24a4`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b1cdb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b20b3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b1cdb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b20b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b1dc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b1dfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b1e44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b1dc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b1dfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b1e44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b1dd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b1e09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b1e51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b1dd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b1e09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b1e51`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800b1cc6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800b1cc6`
- `USER32!PostMessageW` at `0x1800b1e8a`
- `USER32!PostMessageW` at `0x1800b1fd7`
- `USER32!PostMessageW` at `0x1800b207c`
- `USER32!PostMessageW` at `0x1800b1e8a`
- `USER32!PostMessageW` at `0x1800b1fd7`
- `USER32!PostMessageW` at `0x1800b207c`
- `USER32!SetTimer` at `0x1800b2051`
- `USER32!SetTimer` at `0x1800b2051`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800b1d91`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800b1f70`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800b1d91`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800b1f70`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800b1eec`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800b1eec`

## string_xrefs

- `0x1800b1fed`: `CHidPairing::_StartDeviceInstallationServices - Starting necessary services to device installation`
- `0x1800b2033`: `CHidPairing::_StartDeviceInstallationServices - Failed to start deviceinstall: hr=0x%08X`
- `0x1800b2021`: `deviceinstall`
- `0x1800b1d69`: `CHidPairing::_Start - Waiting for discovery to complete`
- `0x1800b1f34`: `CHidPairing::_Start - Waiting for pairing to complete`

## pseudocode

```c

```
