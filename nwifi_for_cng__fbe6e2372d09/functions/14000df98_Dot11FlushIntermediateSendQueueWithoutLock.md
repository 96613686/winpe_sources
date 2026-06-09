# Dot11FlushIntermediateSendQueueWithoutLock

- ea: `0x14000df98`
- end: `0x14000e171`
- name: `Dot11FlushIntermediateSendQueueWithoutLock`
- size: `473`
- prototype: `__int64 __usercall@<rax>(struct _VELAN *@<rcx>, __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d2e0`
- `0x14000d4b0`
- `0x14000e178`
- `0x14000f0b0`
- `0x140011908`
- `0x140011d20`
- `0x140011ea0`

## callees

- `0x14000df98`
- `0x140019314`
- `0x1400327cc`

## import_xrefs

- `NDIS!NdisFSendNetBufferLists` at `0x14000e14c`
- `NDIS!NdisFSendNetBufferLists` at `0x14000e14c`
- `NDIS!NdisReleaseRWLock` at `0x14000e0d4`
- `NDIS!NdisReleaseRWLock` at `0x14000e0d4`
- `NDIS!NdisAcquireRWLockRead` at `0x14000e003`
- `NDIS!NdisAcquireRWLockRead` at `0x14000e003`

## pseudocode

```c

```
