# ScheduleSendMicFailureReport(EXTSTA_VELAN *,DOT11_MAC_STATE_ENTRY *,int)

- ea: `0x14005e070`
- end: `0x14005e1f4`
- name: `?ScheduleSendMicFailureReport@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@H@Z`
- size: `388`
- prototype: `void __fastcall(struct EXTSTA_VELAN *, struct DOT11_MAC_STATE_ENTRY *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005dc5c`

## callees

- `0x14000d21c`
- `0x14005d880`
- `0x14005e070`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005e12d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005e12d`
- `ntoskrnl!ExAllocatePool2` at `0x14005e145`
- `ntoskrnl!ExAllocatePool2` at `0x14005e145`
- `ntoskrnl!IoSizeofWorkItem` at `0x14005e0d2`
- `ntoskrnl!IoSizeofWorkItem` at `0x14005e0d2`
- `ntoskrnl!IoInitializeWorkItem` at `0x14005e172`
- `ntoskrnl!IoInitializeWorkItem` at `0x14005e172`
- `ntoskrnl!IoQueueWorkItem` at `0x14005e1a5`
- `ntoskrnl!IoQueueWorkItem` at `0x14005e1a5`

## pseudocode

```c

```
