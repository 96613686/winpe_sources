# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180011030`
- end: `0x18001113d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000fe7c`
- `0x18000ff80`
- `0x180011030`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800110ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800110ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800110d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800110d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011127`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011127`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011080`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011080`

## string_xrefs

- `0x1800110b3`: `ntdll.dll`
- `0x1800110c7`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
