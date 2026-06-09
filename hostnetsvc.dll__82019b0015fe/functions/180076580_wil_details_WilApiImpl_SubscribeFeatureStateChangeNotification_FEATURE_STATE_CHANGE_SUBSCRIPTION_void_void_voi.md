# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180076580`
- end: `0x18007668d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18007573c`
- `0x180075838`
- `0x180076580`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007660a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007660a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076621`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076621`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180076677`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180076677`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800765d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800765d0`

## string_xrefs

- `0x180076603`: `ntdll.dll`
- `0x180076617`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
