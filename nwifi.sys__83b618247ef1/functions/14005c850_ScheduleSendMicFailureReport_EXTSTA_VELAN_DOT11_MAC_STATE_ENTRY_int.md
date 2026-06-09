# ScheduleSendMicFailureReport(EXTSTA_VELAN *,DOT11_MAC_STATE_ENTRY *,int)

- ea: `0x14005c850`
- end: `0x14005c9d4`
- name: `?ScheduleSendMicFailureReport@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@H@Z`
- size: `388`
- prototype: `void __fastcall(struct EXTSTA_VELAN *, struct DOT11_MAC_STATE_ENTRY *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005c43c`

## callees

- `0x14000d22c`
- `0x14005c060`
- `0x14005c850`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005c90d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005c90d`
- `ntoskrnl!ExAllocatePool2` at `0x14005c925`
- `ntoskrnl!ExAllocatePool2` at `0x14005c925`
- `ntoskrnl!IoSizeofWorkItem` at `0x14005c8b2`
- `ntoskrnl!IoSizeofWorkItem` at `0x14005c8b2`
- `ntoskrnl!IoInitializeWorkItem` at `0x14005c952`
- `ntoskrnl!IoInitializeWorkItem` at `0x14005c952`
- `ntoskrnl!IoQueueWorkItem` at `0x14005c985`
- `ntoskrnl!IoQueueWorkItem` at `0x14005c985`

## pseudocode

```c

```
