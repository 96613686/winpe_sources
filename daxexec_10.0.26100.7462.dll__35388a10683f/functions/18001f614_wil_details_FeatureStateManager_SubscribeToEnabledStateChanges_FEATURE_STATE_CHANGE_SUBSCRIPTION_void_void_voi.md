# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18001f614`
- end: `0x18001f71d`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `265`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001ffa0`

## callees

- `0x18001f614`
- `0x18001f848`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f6a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f6a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f688`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f688`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f64c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f64c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f6f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f6f7`

## string_xrefs

- `0x18001f681`: `ntdll.dll`
- `0x18001f69b`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
