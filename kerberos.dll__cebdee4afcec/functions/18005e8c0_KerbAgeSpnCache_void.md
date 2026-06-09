# KerbAgeSpnCache(void *)

- ea: `0x18005e8c0`
- end: `0x18005e999`
- name: `?KerbAgeSpnCache@@YAKPEAX@Z`
- size: `217`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18002c31c`
- `0x18002d020`
- `0x18005e8c0`
- `0x18008b70c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005e8dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005e8dd`
- `ntdll!RtlReleaseResource` at `0x18005e968`
- `ntdll!RtlReleaseResource` at `0x18005e979`
- `ntdll!RtlReleaseResource` at `0x18005e968`
- `ntdll!RtlReleaseResource` at `0x18005e979`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005e908`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005e908`

## string_xrefs

- `0x18005e8e3`: `Aging the SPN cache\n`
- `0x18005e8f3`: `KerbAgeSpnCache`

## pseudocode

```c

```
