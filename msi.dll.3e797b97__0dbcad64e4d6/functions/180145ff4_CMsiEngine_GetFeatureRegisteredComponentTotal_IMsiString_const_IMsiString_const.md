# CMsiEngine::GetFeatureRegisteredComponentTotal(IMsiString const &,IMsiString const &)

- ea: `0x180145ff4`
- end: `0x180146763`
- name: `?GetFeatureRegisteredComponentTotal@CMsiEngine@@IEAAHAEBVIMsiString@@0@Z`
- size: `1903`
- prototype: `__int64 __fastcall(CMsiEngine *__hidden this, const struct IMsiString *, const struct IMsiString *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18011e4f0`

## callees

- `0x180005af8`
- `0x18000c4bc`
- `0x1800399d0`
- `0x18003bd60`
- `0x18003c030`
- `0x18006cc74`
- `0x18008c93c`
- `0x180145ff4`
- `0x18014676c`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180146060`
- `KERNEL32!InitializeCriticalSection` at `0x180146060`
- `KERNEL32!lstrlenW` at `0x180146102`
- `KERNEL32!lstrlenW` at `0x180146143`
- `KERNEL32!lstrlenW` at `0x180146102`
- `KERNEL32!lstrlenW` at `0x180146143`
- `KERNEL32!GlobalFree` at `0x18014620e`
- `KERNEL32!GlobalFree` at `0x18014665d`
- `KERNEL32!GlobalFree` at `0x18014668e`
- `KERNEL32!GlobalFree` at `0x1801466da`
- `KERNEL32!GlobalFree` at `0x180146713`
- `KERNEL32!GlobalFree` at `0x18014620e`
- `KERNEL32!GlobalFree` at `0x18014665d`
- `KERNEL32!GlobalFree` at `0x18014668e`
- `KERNEL32!GlobalFree` at `0x1801466da`
- `KERNEL32!GlobalFree` at `0x180146713`

## string_xrefs

- `0x18014617b`: `Component`
- `0x1801461cc`: `FeatureComponents`
- `0x180146359`: `Patch Supersedence: Component '%s' is scheduled for removal due to supersedence. Not counting this component as part of the feature '%s'`
- `0x180146606`: `SELMGR: ComponentId '%s' is registered to feature '%s', but is not present in the Component table.  Removal of components from a feature is not supported!`
- `0x18014659b`: `SELMGR: Component '%s' is registered to feature '%s', but is not present in the FeatureComponents table.  Removal of components from a feature is not supported!`

## pseudocode

```c

```
