# RxWaitForStableCondition

- ea: `0x1400621c0`
- end: `0x1400623b6`
- name: `RxWaitForStableCondition`
- size: `502`
- prototype: `void __stdcall(PRX_BLOCK_CONDITION Condition, PLIST_ENTRY TransitionWaitList, PRX_CONTEXT RxContext, NTSTATUS *AsyncStatus)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x140008f60`
- `0x14000daa0`
- `0x14004d498`
- `0x14004dff0`
- `0x14004fef0`
- `0x14005f400`
- `0x140060560`
- `0x140078fe0`

## callees

- `0x140010980`
- `0x140017540`
- `0x14001bd9c`
- `0x1400621c0`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x140062205`
- `ntoskrnl!KeResetEvent` at `0x140062205`
- `ntoskrnl!KeReleaseMutex` at `0x1400622ab`
- `ntoskrnl!KeReleaseMutex` at `0x1400622f5`
- `ntoskrnl!KeReleaseMutex` at `0x1400622ab`
- `ntoskrnl!KeReleaseMutex` at `0x1400622f5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140062231`
- `ntoskrnl!KeWaitForSingleObject` at `0x140062398`
- `ntoskrnl!KeWaitForSingleObject` at `0x140062231`
- `ntoskrnl!KeWaitForSingleObject` at `0x140062398`

## pseudocode

```c

```
