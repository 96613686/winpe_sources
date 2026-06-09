# DsRolepCheckServiceTimeout

- ea: `0x18000f510`
- end: `0x18000f57b`
- name: `DsRolepCheckServiceTimeout`
- size: `107`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000f510`
- `0x18000fee4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f51a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f51a`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000f535`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000f535`
- `ntdll!RtlReleaseResource` at `0x18000f548`
- `ntdll!RtlReleaseResource` at `0x18000f548`

## pseudocode

```c

```
