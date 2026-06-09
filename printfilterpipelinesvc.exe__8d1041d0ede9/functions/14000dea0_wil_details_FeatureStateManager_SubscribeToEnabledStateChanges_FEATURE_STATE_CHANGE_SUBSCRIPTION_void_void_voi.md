# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000dea0`
- end: `0x14000df67`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000e610`

## callees

- `0x1400094d4`
- `0x14000dea0`
- `0x14000e064`
- `0x14000f070`
- `0x140063010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ded5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ded5`

## string_xrefs

- `0x14000df00`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
