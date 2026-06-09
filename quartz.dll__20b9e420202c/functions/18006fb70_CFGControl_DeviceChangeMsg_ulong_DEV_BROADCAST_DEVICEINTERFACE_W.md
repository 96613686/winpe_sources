# CFGControl::DeviceChangeMsg(ulong,_DEV_BROADCAST_DEVICEINTERFACE_W *)

- ea: `0x18006fb70`
- end: `0x18006fd19`
- name: `?DeviceChangeMsg@CFGControl@@QEAAXKPEAU_DEV_BROADCAST_DEVICEINTERFACE_W@@@Z`
- size: `425`
- prototype: `void __fastcall(CFGControl *__hidden this, unsigned int, struct _DEV_BROADCAST_DEVICEINTERFACE_W *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180018f70`

## callees

- `0x180013810`
- `0x1800197c0`
- `0x1800388a0`
- `0x18006fb70`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18006fce8`
- `KERNEL32!LeaveCriticalSection` at `0x18006fce8`
- `KERNEL32!EnterCriticalSection` at `0x18006fbad`
- `KERNEL32!EnterCriticalSection` at `0x18006fbad`
- `KERNEL32!lstrcmpiW` at `0x18006fc3c`
- `KERNEL32!lstrcmpiW` at `0x18006fc3c`
- `ole32!CoTaskMemFree` at `0x18006fc5a`
- `ole32!CoTaskMemFree` at `0x18006fc5a`

## pseudocode

```c

```
