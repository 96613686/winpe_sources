# NGENService::EventLog(ushort const *,ushort,ulong,ushort const *,...)

- ea: `0x18002e418`
- end: `0x18002e535`
- name: `?EventLog@NGENService@@YAXPEBGGK0ZZ`
- size: `285`
- prototype: `void(NGENService *__hidden this, const unsigned __int16 *, unsigned __int16, unsigned int, const unsigned __int16 *, ...)`
- caller_count: `10`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180002f44`
- `0x180003270`
- `0x180004cac`
- `0x1800053a0`
- `0x180005688`
- `0x180011e5c`
- `0x18001b1e4`
- `0x18001b340`
- `0x18002587c`
- `0x18004158c`

## callees

- `0x18002dfa0`
- `0x18002e418`
- `0x180030d84`
- `0x180032678`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002e465`
- `KERNEL32!EnterCriticalSection` at `0x18002e465`
- `KERNEL32!LeaveCriticalSection` at `0x18002e510`
- `KERNEL32!LeaveCriticalSection` at `0x18002e510`
- `KERNEL32!HeapFree` at `0x18002e506`
- `KERNEL32!HeapFree` at `0x18002e506`
- `KERNEL32!GetProcessHeap` at `0x18002e4f1`
- `KERNEL32!GetProcessHeap` at `0x18002e4f1`

## pseudocode

```c

```
