# CMsiEngine::GetFeatureRegisteredComponentTotal(IMsiString const &,IMsiString const &)

- ea: `0x180140d48`
- end: `0x180141486`
- name: `?GetFeatureRegisteredComponentTotal@CMsiEngine@@IEAAHAEBVIMsiString@@0@Z`
- size: `1854`
- prototype: `__int64 __fastcall(CMsiEngine *__hidden this, const struct IMsiString *, const struct IMsiString *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180118160`

## callees

- `0x180015690`
- `0x180015950`
- `0x180025a18`
- `0x18004295c`
- `0x180050cf0`
- `0x180066074`
- `0x180073cc0`
- `0x180140d48`
- `0x18014148c`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180140db4`
- `KERNEL32!InitializeCriticalSection` at `0x180140db4`
- `KERNEL32!lstrlenW` at `0x180140e50`
- `KERNEL32!lstrlenW` at `0x180140e8b`
- `KERNEL32!lstrlenW` at `0x180140e50`
- `KERNEL32!lstrlenW` at `0x180140e8b`
- `KERNEL32!GlobalFree` at `0x180140f50`
- `KERNEL32!GlobalFree` at `0x180141399`
- `KERNEL32!GlobalFree` at `0x1801413c4`
- `KERNEL32!GlobalFree` at `0x18014140a`
- `KERNEL32!GlobalFree` at `0x18014143d`
- `KERNEL32!GlobalFree` at `0x180140f50`
- `KERNEL32!GlobalFree` at `0x180141399`
- `KERNEL32!GlobalFree` at `0x1801413c4`
- `KERNEL32!GlobalFree` at `0x18014140a`
- `KERNEL32!GlobalFree` at `0x18014143d`

## string_xrefs

- `0x180140ebd`: `Component`
- `0x180140f0e`: `FeatureComponents`
- `0x180141095`: `Patch Supersedence: Component '%s' is scheduled for removal due to supersedence. Not counting this component as part of the feature '%s'`
- `0x180141342`: `SELMGR: ComponentId '%s' is registered to feature '%s', but is not present in the Component table.  Removal of components from a feature is not supported!`
- `0x1801412d7`: `SELMGR: Component '%s' is registered to feature '%s', but is not present in the FeatureComponents table.  Removal of components from a feature is not supported!`

## pseudocode

```c

```
