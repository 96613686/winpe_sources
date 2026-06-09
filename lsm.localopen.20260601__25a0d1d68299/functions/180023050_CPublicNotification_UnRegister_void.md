# CPublicNotification::UnRegister(void)

- ea: `0x180023050`
- end: `0x1800232b1`
- name: `?UnRegister@CPublicNotification@@UEAAJXZ`
- size: `609`
- prototype: `__int64 __fastcall(CPublicNotification *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180022f3c`

## callees

- `0x180023050`
- `0x180024aa0`
- `0x18004e850`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180023214`
- `ntdll!RtlReleaseResource` at `0x180023285`
- `ntdll!RtlReleaseResource` at `0x180023214`
- `ntdll!RtlReleaseResource` at `0x180023285`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800231b2`
- `ntdll!RtlAcquireResourceExclusive` at `0x180023247`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800231b2`
- `ntdll!RtlAcquireResourceExclusive` at `0x180023247`
- `ntdll!EtwEventWriteTransfer` at `0x180023191`
- `ntdll!EtwEventWriteTransfer` at `0x180023191`

## pseudocode

```c

```
