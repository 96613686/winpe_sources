# Dot11FlushIntermediateSendQueueWithoutLock

- ea: `0x14000dfa8`
- end: `0x14000e181`
- name: `Dot11FlushIntermediateSendQueueWithoutLock`
- size: `473`
- prototype: `__int64 __usercall@<rax>(struct _VELAN *@<rcx>, __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d2f0`
- `0x14000d4c0`
- `0x14000e188`
- `0x14000f0c0`
- `0x140011918`
- `0x140011d30`
- `0x140011eb0`

## callees

- `0x14000dfa8`
- `0x140019314`
- `0x1400325ac`

## import_xrefs

- `NDIS!NdisFSendNetBufferLists` at `0x14000e15c`
- `NDIS!NdisFSendNetBufferLists` at `0x14000e15c`
- `NDIS!NdisReleaseRWLock` at `0x14000e0e4`
- `NDIS!NdisReleaseRWLock` at `0x14000e0e4`
- `NDIS!NdisAcquireRWLockRead` at `0x14000e013`
- `NDIS!NdisAcquireRWLockRead` at `0x14000e013`

## pseudocode

```c

```
