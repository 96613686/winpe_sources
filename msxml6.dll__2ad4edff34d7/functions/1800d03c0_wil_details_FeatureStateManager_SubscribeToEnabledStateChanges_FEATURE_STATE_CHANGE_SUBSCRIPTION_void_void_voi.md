# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800d03c0`
- end: `0x1800d0487`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, FEATURE_STATE_CHANGE_SUBSCRIPTION__ **subscription, void (__fastcall *callback)(void *), void *context)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800d0a20`

## callees

- `0x1800ba178`
- `0x1800d03c0`
- `0x1800d0584`
- `0x1800d1060`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d03f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d03f5`

## string_xrefs

- `0x1800d0420`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
