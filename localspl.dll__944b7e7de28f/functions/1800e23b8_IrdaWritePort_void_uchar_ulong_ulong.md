# IrdaWritePort(void *,uchar *,ulong,ulong *)

- ea: `0x1800e23b8`
- end: `0x1800e25e8`
- name: `?IrdaWritePort@@YAHPEAXPEAEKPEAK@Z`
- size: `560`
- prototype: `__int64 __fastcall(struct _LCMINIPORT *, unsigned __int8 *Src, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800df1b0`

## callees

- `0x180047318`
- `0x1800df3e0`
- `0x1800df488`
- `0x1800e1ee0`
- `0x1800e23b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e2469`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e2469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e25ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e25ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e25c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e25c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800e2433`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800e244d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800e2433`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800e244d`
- `SPOOLSS!SetJobW` at `0x1800e2423`
- `SPOOLSS!SetJobW` at `0x1800e2423`
- `WS2_32!WSASend` at `0x1800e2539`
- `WS2_32!WSASend` at `0x1800e2539`
- `WS2_32!WSAGetOverlappedResult` at `0x1800e2497`
- `WS2_32!WSAGetOverlappedResult` at `0x1800e2497`
- `WS2_32!WSACloseEvent` at `0x1800e24b8`
- `WS2_32!WSACloseEvent` at `0x1800e24b8`
- `WS2_32!WSACreateEvent` at `0x1800e24cb`
- `WS2_32!WSACreateEvent` at `0x1800e24cb`
- `WS2_32!WSAResetEvent` at `0x1800e24a9`
- `WS2_32!WSAResetEvent` at `0x1800e24a9`
- `WS2_32!__imp_WSAGetLastError` at `0x1800e2555`
- `WS2_32!__imp_WSAGetLastError` at `0x1800e259a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800e2555`
- `WS2_32!__imp_WSAGetLastError` at `0x1800e259a`

## string_xrefs

- `0x1800e23f0`: `IrdaWritePort`
- `0x1800e257d`: `IrdaWritePort`

## pseudocode

```c

```
