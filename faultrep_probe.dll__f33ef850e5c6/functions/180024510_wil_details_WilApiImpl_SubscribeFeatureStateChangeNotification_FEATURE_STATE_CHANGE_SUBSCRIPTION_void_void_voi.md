# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180024510`
- end: `0x18002461d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180023e1c`
- `0x180023f18`
- `0x180024510`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002459a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002459a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800245b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800245b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024560`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024560`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024607`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024607`

## string_xrefs

- `0x180024593`: `ntdll.dll`
- `0x1800245a7`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
