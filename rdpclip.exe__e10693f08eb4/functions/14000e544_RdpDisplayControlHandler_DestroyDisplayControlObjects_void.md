# RdpDisplayControlHandler::DestroyDisplayControlObjects(void)

- ea: `0x14000e544`
- end: `0x14000e850`
- name: `?DestroyDisplayControlObjects@RdpDisplayControlHandler@@AEAAJXZ`
- size: `780`
- prototype: `__int64 __fastcall(RdpDisplayControlHandler *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x14000fe28`
- `0x1400103e8`

## callees

- `0x140004b1c`
- `0x140004cf4`
- `0x140005704`
- `0x140005750`
- `0x1400081ac`
- `0x1400081d0`
- `0x14000e544`
- `0x14001096c`
- `0x140010998`
- `0x140020d00`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e7df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e7df`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000e58a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000e58a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e7d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e7d5`

## string_xrefs

- `0x14000e616`: `ITSThread::DestroyThread (m_spDisplayControlProcessThread) failed`
- `0x14000e697`: `ITSCoreEventSource::RemoveNotificationSource (m_spMonitorLayoutChangeRequestedEventSource) failed`

## pseudocode

```c

```
