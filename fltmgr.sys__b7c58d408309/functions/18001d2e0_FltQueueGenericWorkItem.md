# FltQueueGenericWorkItem

- ea: `0x18001d2e0`
- end: `0x18001d440`
- name: `FltQueueGenericWorkItem`
- size: `352`
- prototype: `NTSTATUS __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PFLT_GENERIC_WORKITEM_ROUTINE WorkerRoutine, WORK_QUEUE_TYPE QueueType, PVOID Context)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x1800147b0`
- `0x18001d2e0`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x18001d412`
- `ntoskrnl!ExQueueWorkItem` at `0x18001d412`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x18001d346`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x18001d346`
- `ntoskrnl!IoGetActivityIdThread` at `0x18001d359`
- `ntoskrnl!IoGetActivityIdThread` at `0x18001d359`

## pseudocode

```c

```
