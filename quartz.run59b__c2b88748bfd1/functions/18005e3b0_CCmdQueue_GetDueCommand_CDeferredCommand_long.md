# CCmdQueue::GetDueCommand(CDeferredCommand * *,long)

- ea: `0x18005e3b0`
- end: `0x18005e491`
- name: `?GetDueCommand@CCmdQueue@@UEAAJPEAPEAVCDeferredCommand@@J@Z`
- size: `225`
- prototype: `int(CCmdQueue *__hidden this, struct CDeferredCommand **, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18005df24`
- `0x18005e3b0`
- `0x18015e010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18005e446`
- `KERNEL32!WaitForSingleObject` at `0x18005e446`
- `KERNEL32!LeaveCriticalSection` at `0x18005e431`
- `KERNEL32!LeaveCriticalSection` at `0x18005e481`
- `KERNEL32!LeaveCriticalSection` at `0x18005e431`
- `KERNEL32!LeaveCriticalSection` at `0x18005e481`
- `KERNEL32!EnterCriticalSection` at `0x18005e3cb`
- `KERNEL32!EnterCriticalSection` at `0x18005e3cb`

## pseudocode

```c

```
