# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18002048c`
- end: `0x180020584`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180020e20`

## callees

- `0x18002048c`
- `0x1800206a0`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800204fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800204fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020518`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020518`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800204bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800204bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002056a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002056a`

## string_xrefs

- `0x1800204f4`: `ntdll.dll`
- `0x18002050e`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
