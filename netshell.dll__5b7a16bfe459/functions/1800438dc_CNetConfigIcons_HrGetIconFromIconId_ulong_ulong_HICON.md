# CNetConfigIcons::HrGetIconFromIconId(ulong,ulong,HICON__ * &)

- ea: `0x1800438dc`
- end: `0x1800439d3`
- name: `?HrGetIconFromIconId@CNetConfigIcons@@QEAAJKKAEAPEAUHICON__@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(CNetConfigIcons *__hidden this, unsigned int, unsigned int, HICON *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800439dc`
- `0x18004bb40`

## callees

- `0x1800066b0`
- `0x1800179f0`
- `0x1800438dc`
- `0x180043cc0`

## import_xrefs

- `USER32!LoadImageW` at `0x180043951`
- `USER32!LoadImageW` at `0x180043951`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800439b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800439b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043905`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004395f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004395f`

## pseudocode

```c

```
