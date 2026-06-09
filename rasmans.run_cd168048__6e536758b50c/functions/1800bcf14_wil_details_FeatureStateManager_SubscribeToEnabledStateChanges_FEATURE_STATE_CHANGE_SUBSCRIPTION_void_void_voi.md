# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800bcf14`
- end: `0x1800bd00c`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800bd850`

## callees

- `0x1800bcf14`
- `0x1800bd128`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bcff2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bcff2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bcf44`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bcf44`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800bcf83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800bcf83`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bcfa0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bcfa0`

## string_xrefs

- `0x1800bcf7c`: `ntdll.dll`
- `0x1800bcf96`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
