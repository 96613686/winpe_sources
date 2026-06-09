# FvepQueueWorkItem

- ea: `0x14002cac0`
- end: `0x14002cf1c`
- name: `FvepQueueWorkItem`
- size: `1116`
- prototype: `__int64 __usercall@<rax>(PVOID Context@<rcx>, ULONG_PTR BugCheckParameter2@<rdx>, int, char, __int64, __int64, __int64, int, char)`
- caller_count: `17`
- callee_count: `4`
- tags: ``

## callers

- `0x14002a3f0`
- `0x14002b6e0`
- `0x14002b9a8`
- `0x14006f058`
- `0x140084504`
- `0x1400c3370`
- `0x1400c4de8`
- `0x1400c5f08`
- `0x1400d0a20`
- `0x1400d2f60`
- `0x1400d92d0`
- `0x1400da368`
- `0x1400daf30`
- `0x1400de048`
- `0x1400de940`
- `0x1400e1900`
- `0x1400e7880`

## callees

- `0x140022cd0`
- `0x14002cac0`
- `0x14002cf30`
- `0x14002d8f0`

## import_xrefs

- `ntoskrnl!IoQueueWorkItemEx` at `0x14002cbd2`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14002cbd2`
- `ntoskrnl!KeReleaseSemaphore` at `0x14002ce6a`
- `ntoskrnl!KeReleaseSemaphore` at `0x14002ce6a`
- `ntoskrnl!IoTryQueueWorkItem` at `0x14002cd4b`
- `ntoskrnl!IoTryQueueWorkItem` at `0x14002cd4b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002cc04`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002cc76`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002cd19`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ce33`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002cc04`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002cc76`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002cd19`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ce33`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002caef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002cd8a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002caef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002cd8a`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14002ce50`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14002ce50`
- `ntoskrnl!KeBugCheckEx` at `0x14002cca8`
- `ntoskrnl!KeBugCheckEx` at `0x14002ce9c`
- `ntoskrnl!KeBugCheckEx` at `0x14002cecf`
- `ntoskrnl!KeBugCheckEx` at `0x14002cca8`
- `ntoskrnl!KeBugCheckEx` at `0x14002ce9c`
- `ntoskrnl!KeBugCheckEx` at `0x14002cecf`

## pseudocode

```c

```
