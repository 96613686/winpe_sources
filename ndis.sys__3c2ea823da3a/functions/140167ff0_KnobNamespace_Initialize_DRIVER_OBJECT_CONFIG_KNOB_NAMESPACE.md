# KnobNamespace::Initialize(_DRIVER_OBJECT *,_CONFIG_KNOB_NAMESPACE *)

- ea: `0x140167ff0`
- end: `0x14016808e`
- name: `?Initialize@KnobNamespace@@QEAAXPEAU_DRIVER_OBJECT@@PEAU_CONFIG_KNOB_NAMESPACE@@@Z`
- size: `158`
- prototype: `void __fastcall(KnobNamespace *__hidden this, struct _DRIVER_OBJECT *, struct _CONFIG_KNOB_NAMESPACE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140167fa0`

## callees

- `0x140167ff0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016807b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016807b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140168016`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140168016`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14016802b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14016802b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14016806f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14016806f`

## pseudocode

```c

```
