# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800103f0`
- end: `0x1800104fd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000f95c`
- `0x18000fa58`
- `0x1800103f0`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010491`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010491`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001047a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001047a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010440`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010440`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800104e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800104e7`

## string_xrefs

- `0x180010473`: `ntdll.dll`
- `0x180010487`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
