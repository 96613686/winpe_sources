# RasConnectCallback(ulong,ulong,HRASCONN__ *,ulong,tagRASCONNSTATE,ulong,ulong)

- ea: `0x18000d840`
- end: `0x18000e325`
- name: `?RasConnectCallback@@YAHKKPEAUHRASCONN__@@KW4tagRASCONNSTATE@@KK@Z`
- size: `2789`
- prototype: `int(unsigned int, unsigned int, HRASCONN, unsigned int, enum tagRASCONNSTATE, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x180007b7c`
- `0x180007c50`
- `0x180008e08`
- `0x18000d840`
- `0x18000ed5c`
- `0x18001f4e0`
- `0x18003b7a8`
- `0x18003b8f4`
- `0x180071cec`
- `0x180073664`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18000da29`
- `msvcrt!_itow_s` at `0x18000dc15`
- `msvcrt!_itow_s` at `0x18000dd85`
- `msvcrt!_itow_s` at `0x18000de54`
- `msvcrt!_itow_s` at `0x18000da29`
- `msvcrt!_itow_s` at `0x18000dc15`
- `msvcrt!_itow_s` at `0x18000dd85`
- `msvcrt!_itow_s` at `0x18000de54`
- `msvcrt!time` at `0x18000e00a`
- `msvcrt!time` at `0x18000e00a`
- `msvcrt!rand` at `0x18000e032`
- `msvcrt!rand` at `0x18000e032`
- `msvcrt!srand` at `0x18000e013`
- `msvcrt!srand` at `0x18000e013`
- `KERNEL32!SetEvent` at `0x18000e27e`
- `KERNEL32!SetEvent` at `0x18000e27e`
- `KERNEL32!LeaveCriticalSection` at `0x18000e2c1`
- `KERNEL32!LeaveCriticalSection` at `0x18000e2c1`
- `KERNEL32!EnterCriticalSection` at `0x18000dce0`
- `KERNEL32!EnterCriticalSection` at `0x18000dce0`
- `RASAPI32!RasGetSubEntryHandleW` at `0x18000d954`
- `RASAPI32!RasGetSubEntryHandleW` at `0x18000d954`
- `RASAPI32!RasHangUpW` at `0x18000df52`
- `RASAPI32!RasHangUpW` at `0x18000df52`
- `RASAPI32!RasGetHport` at `0x18000dc8f`
- `RASAPI32!RasGetHport` at `0x18000dc8f`
- `rtutils!RouterLogEventStringW` at `0x18000e24b`
- `rtutils!RouterLogEventStringW` at `0x18000e24b`

## string_xrefs

- `0x18000de6c`: `RasConnectCallback:RASCS_PortOpened,dwSubEntryId=%d,hPort=%d., fFlag:0x%x`

## pseudocode

```c

```
