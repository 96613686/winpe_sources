# BaseRegSetValueInternal

- ea: `0x1800a7d00`
- end: `0x1800a7fa3`
- name: `BaseRegSetValueInternal`
- size: `675`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName, ULONG Type, PVOID Data, ULONG)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18002e7d0`
- `0x1800a6610`

## callees

- `0x180061220`
- `0x1800a7d00`
- `0x180136e28`
- `0x180139854`
- `0x18018f578`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800a7e5d`
- `ntdll!RtlNtStatusToDosError` at `0x1800a7f92`
- `ntdll!RtlNtStatusToDosError` at `0x18019ea4a`
- `ntdll!RtlNtStatusToDosError` at `0x1800a7e5d`
- `ntdll!RtlNtStatusToDosError` at `0x1800a7f92`
- `ntdll!RtlNtStatusToDosError` at `0x18019ea4a`
- `ntdll!NtSetValueKey` at `0x1800a7e2f`
- `ntdll!NtSetValueKey` at `0x18019ea1a`
- `ntdll!NtSetValueKey` at `0x18019eaaa`
- `ntdll!NtSetValueKey` at `0x1800a7e2f`
- `ntdll!NtSetValueKey` at `0x18019ea1a`
- `ntdll!NtSetValueKey` at `0x18019eaaa`
- `ntdll!NtClose` at `0x1800a7f12`
- `ntdll!NtClose` at `0x18019eabd`
- `ntdll!NtClose` at `0x1800a7f12`
- `ntdll!NtClose` at `0x18019eabd`
- `ntdll!RtlFreeHeap` at `0x18019ea3c`
- `ntdll!RtlFreeHeap` at `0x18019ea3c`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegSetValue` at `0x1800a7ec1`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegSetValue` at `0x1800a7ec1`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvGetPreSetValue` at `0x1800a7dc0`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvGetPreSetValue` at `0x1800a7dc0`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvSetValueKey` at `0x1800a7df7`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvSetValueKey` at `0x1800a7df7`

## pseudocode

```c

```
