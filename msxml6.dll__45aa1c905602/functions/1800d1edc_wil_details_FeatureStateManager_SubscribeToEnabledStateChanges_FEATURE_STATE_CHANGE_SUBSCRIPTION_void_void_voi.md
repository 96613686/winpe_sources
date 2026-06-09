# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800d1edc`
- end: `0x1800d1faa`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `206`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, FEATURE_STATE_CHANGE_SUBSCRIPTION__ **subscription, void (__fastcall *callback)(void *), void *context)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800d25d0`

## callees

- `0x1800bb844`
- `0x1800d1edc`
- `0x1800d20b0`
- `0x1800d2c5c`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d1f11`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d1f11`

## string_xrefs

- `0x1800d1f42`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
