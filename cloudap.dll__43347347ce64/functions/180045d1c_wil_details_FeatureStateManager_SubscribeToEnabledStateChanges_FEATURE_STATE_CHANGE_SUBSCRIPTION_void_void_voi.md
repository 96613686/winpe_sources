# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180045d1c`
- end: `0x180045dd7`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `187`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180046270`

## callees

- `0x18003b148`
- `0x180040f54`
- `0x180045d1c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180045dc4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180045dc4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180045d4c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180045d4c`

## string_xrefs

- `0x180045d72`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
