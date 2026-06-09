# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180013240`
- end: `0x18001334d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180012a8c`
- `0x180012b88`
- `0x180013240`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800132e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800132e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800132ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800132ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013337`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013337`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013290`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013290`

## string_xrefs

- `0x1800132c3`: `ntdll.dll`
- `0x1800132d7`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
