# RasConnectCallback(ulong,ulong,HRASCONN__ *,ulong,tagRASCONNSTATE,ulong,ulong)

- ea: `0x18000dc90`
- end: `0x18000e809`
- name: `?RasConnectCallback@@YAHKKPEAUHRASCONN__@@KW4tagRASCONNSTATE@@KK@Z`
- size: `2937`
- prototype: `int(unsigned int, unsigned int, HRASCONN, unsigned int, enum tagRASCONNSTATE, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x180007c0c`
- `0x180007d00`
- `0x180008efc`
- `0x18000dc90`
- `0x18000f254`
- `0x180020130`
- `0x18003d100`
- `0x18003d278`
- `0x180075588`
- `0x1800755b8`
- `0x1800771b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!time` at `0x18000e4b8`
- `msvcrt!time` at `0x18000e4b8`
- `msvcrt!rand` at `0x18000e4ec`
- `msvcrt!rand` at `0x18000e4ec`
- `msvcrt!srand` at `0x18000e4c7`
- `msvcrt!srand` at `0x18000e4c7`
- `KERNEL32!SetEvent` at `0x18000e754`
- `KERNEL32!SetEvent` at `0x18000e754`
- `KERNEL32!LeaveCriticalSection` at `0x18000e7a2`
- `KERNEL32!LeaveCriticalSection` at `0x18000e7a2`
- `KERNEL32!EnterCriticalSection` at `0x18000df18`
- `KERNEL32!EnterCriticalSection` at `0x18000df18`
- `RASAPI32!RasGetSubEntryHandleW` at `0x18000ddd7`
- `RASAPI32!RasGetSubEntryHandleW` at `0x18000ddd7`
- `RASAPI32!RasHangUpW` at `0x18000e3f8`
- `RASAPI32!RasHangUpW` at `0x18000e3f8`
- `RASAPI32!RasGetHport` at `0x18000dec1`
- `RASAPI32!RasGetHport` at `0x18000dec1`
- `rtutils!RouterLogEventStringW` at `0x18000e71b`
- `rtutils!RouterLogEventStringW` at `0x18000e71b`

## string_xrefs

- `0x18000e09d`: `RasConnectCallback:RASCS_PortOpened,dwSubEntryId=%d,hPort=%d., fFlag:0x%x`

## pseudocode

```c

```
