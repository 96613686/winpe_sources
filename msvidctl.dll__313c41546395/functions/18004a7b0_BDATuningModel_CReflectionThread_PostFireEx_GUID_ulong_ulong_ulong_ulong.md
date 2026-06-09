# BDATuningModel::CReflectionThread::PostFireEx(_GUID &,ulong,ulong,ulong,ulong)

- ea: `0x18004a7b0`
- end: `0x18004a88a`
- name: `?PostFireEx@CReflectionThread@BDATuningModel@@QEAAJAEAU_GUID@@KKKK@Z`
- size: `218`
- prototype: `__int64 __fastcall(BDATuningModel::CReflectionThread *__hidden this, struct _GUID *, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18004a5f0`

## callees

- `0x180004640`
- `0x18004a7b0`
- `0x18004ad64`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18004a843`
- `KERNEL32!SetEvent` at `0x18004a843`
- `KERNEL32!LeaveCriticalSection` at `0x18004a84d`
- `KERNEL32!LeaveCriticalSection` at `0x18004a85c`
- `KERNEL32!LeaveCriticalSection` at `0x18004a84d`
- `KERNEL32!LeaveCriticalSection` at `0x18004a85c`
- `KERNEL32!EnterCriticalSection` at `0x18004a7ef`
- `KERNEL32!EnterCriticalSection` at `0x18004a7ef`

## pseudocode

```c

```
