# SocketIoMonitor::GetDuplicatedSocket(ulong,uchar,_SOCKET_BROKER_RETRIEVE_SOCKET * *)

- ea: `0x180013cb0`
- end: `0x180013d59`
- name: `?GetDuplicatedSocket@SocketIoMonitor@@UEAAKKEPEAPEAU_SOCKET_BROKER_RETRIEVE_SOCKET@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, DWORD, __int64, struct _SOCKET_BROKER_RETRIEVE_SOCKET **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000a0a0`
- `0x180013cb0`
- `0x180013f04`
- `0x1800143a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ccf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ccf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013d16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013d16`

## pseudocode

```c

```
