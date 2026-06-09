# KnobNamespace::Initialize(_DRIVER_OBJECT *,_CONFIG_KNOB_NAMESPACE *)

- ea: `0x14016eee0`
- end: `0x14016ef7e`
- name: `?Initialize@KnobNamespace@@QEAAXPEAU_DRIVER_OBJECT@@PEAU_CONFIG_KNOB_NAMESPACE@@@Z`
- size: `158`
- prototype: `void __fastcall(KnobNamespace *__hidden this, struct _DRIVER_OBJECT *, struct _CONFIG_KNOB_NAMESPACE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14016ee90`

## callees

- `0x14016eee0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016ef6b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016ef6b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14016ef06`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14016ef06`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14016ef1b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14016ef1b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14016ef5f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14016ef5f`

## pseudocode

```c

```
