# PmWmiCounterEnable(_PERF_COUNTER_CONTEXT * *)

- ea: `0x14001c2c0`
- end: `0x14001c3b5`
- name: `?PmWmiCounterEnable@@YAJPEAPEAU_PERF_COUNTER_CONTEXT@@@Z`
- size: `245`
- prototype: `__int64 __fastcall(struct _PERF_COUNTER_CONTEXT **)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007674`
- `0x14001dfcc`
- `0x1400203c0`
- `0x140024fd4`

## callees

- `0x14001c2c0`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14001c2fd`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14001c381`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14001c2fd`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14001c381`
- `ntoskrnl!KeInitializeMutex` at `0x14001c39a`
- `ntoskrnl!KeInitializeMutex` at `0x14001c39a`
- `ntoskrnl!ExAllocatePool2` at `0x14001c352`
- `ntoskrnl!ExAllocatePool2` at `0x14001c352`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14001c32a`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14001c32a`

## pseudocode

```c

```
