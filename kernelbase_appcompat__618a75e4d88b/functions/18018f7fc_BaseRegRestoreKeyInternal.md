# BaseRegRestoreKeyInternal

- ea: `0x18018f7fc`
- end: `0x18018fa36`
- name: `BaseRegRestoreKeyInternal`
- size: `570`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x18014a8c0`
- `0x18014aa10`

## callees

- `0x180061910`
- `0x180139854`
- `0x18018f7fc`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18018f886`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18018f886`
- `ntdll!RtlReleaseRelativeName` at `0x18018f923`
- `ntdll!RtlReleaseRelativeName` at `0x18018f923`
- `ntdll!NtOpenFile` at `0x18018f911`
- `ntdll!NtOpenFile` at `0x18018f911`
- `ntdll!RtlNtStatusToDosError` at `0x18018fa0b`
- `ntdll!RtlNtStatusToDosError` at `0x18018fa0b`
- `ntdll!NtClose` at `0x18018f9ad`
- `ntdll!NtClose` at `0x18018f9d4`
- `ntdll!NtClose` at `0x18018f9ad`
- `ntdll!NtClose` at `0x18018f9d4`
- `ntdll!RtlFreeHeap` at `0x18018f941`
- `ntdll!RtlFreeHeap` at `0x18018f941`
- `ntdll!NtRestoreKey` at `0x18018f99b`
- `ntdll!NtRestoreKey` at `0x18018f9c2`
- `ntdll!NtRestoreKey` at `0x18018f99b`
- `ntdll!NtRestoreKey` at `0x18018f9c2`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvRestoreKey` at `0x18018f9fd`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvRestoreKey` at `0x18018f9fd`

## pseudocode

```c

```
