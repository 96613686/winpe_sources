# KerbSocketChangeHandler(void *,uchar)

- ea: `0x180091810`
- end: `0x1800919f2`
- name: `?KerbSocketChangeHandler@@YAXPEAXE@Z`
- size: `482`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x18002d190`
- `0x18003003c`
- `0x18004fd50`
- `0x180065c70`
- `0x18008b70c`
- `0x180091810`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18009192c`
- `ntdll!RtlReleaseResource` at `0x18009192c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180091918`
- `ntdll!RtlAcquireResourceExclusive` at `0x180091918`
- `ntdll!RtlEnterCriticalSection` at `0x180091939`
- `ntdll!RtlEnterCriticalSection` at `0x180091939`
- `ntdll!RtlLeaveCriticalSection` at `0x1800919d9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800919d9`

## string_xrefs

- `0x1800918b6`: `KerbIsTcpNotInstalled failed with 0x%x\n`
- `0x18009186f`: `KerbPurgeKdcProxyCacheWorker3 failed with status 0x%x\n`
- `0x18009188e`: `KdcProxyCache is purged: %d / %d entries purged\n`

## pseudocode

```c

```
