# CCallbackThread::AdvisePeriodicWithEvent(void (*)(unsigned __int64),unsigned __int64,__int64,void *,unsigned __int64 *)

- ea: `0x180030cd0`
- end: `0x180030d72`
- name: `?AdvisePeriodicWithEvent@CCallbackThread@@QEAAJP6AX_K@Z0_JPEAXPEA_K@Z`
- size: `162`
- prototype: `__int64 __usercall@<rax>(CCallbackThread *__hidden this@<rcx>, void (*)(unsigned __int64)@<rdx>, unsigned __int64@<r8>, __int64@<r9>, void *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180030c98`

## callees

- `0x180030cd0`
- `0x180141934`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180030d39`
- `KERNEL32!SetEvent` at `0x180030d39`
- `KERNEL32!LeaveCriticalSection` at `0x180030d5a`
- `KERNEL32!LeaveCriticalSection` at `0x180030d5a`
- `KERNEL32!EnterCriticalSection` at `0x180030ce6`
- `KERNEL32!EnterCriticalSection` at `0x180030ce6`
- `WINMM!timeGetTime` at `0x180030d0d`
- `WINMM!timeGetTime` at `0x180030d0d`

## pseudocode

```c

```
