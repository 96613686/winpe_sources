# CESEventService::FindConnectionPoint(_GUID const &,IConnectionPoint * *)

- ea: `0x18004c960`
- end: `0x18004cacb`
- name: `?FindConnectionPoint@CESEventService@@UEAAJAEBU_GUID@@PEAPEAUIConnectionPoint@@@Z`
- size: `363`
- prototype: `int(CESEventService *__hidden this, const struct _GUID *, struct IConnectionPoint **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180006b38`
- `0x18000e518`
- `0x18004b634`
- `0x18004c07c`
- `0x18004c474`
- `0x18004c960`
- `0x18004ccf4`
- `0x1800f8010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18004caa2`
- `KERNEL32!LeaveCriticalSection` at `0x18004caa2`
- `KERNEL32!EnterCriticalSection` at `0x18004c984`
- `KERNEL32!EnterCriticalSection` at `0x18004c984`

## pseudocode

```c

```
