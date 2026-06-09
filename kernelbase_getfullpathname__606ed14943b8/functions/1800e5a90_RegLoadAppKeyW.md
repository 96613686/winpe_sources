# RegLoadAppKeyW

- ea: `0x1800e5a90`
- end: `0x1800e5cc8`
- name: `RegLoadAppKeyW`
- size: `568`
- prototype: `LSTATUS __stdcall(LPCWSTR lpFile, PHKEY phkResult, REGSAM samDesired, DWORD dwOptions, DWORD Reserved)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x18011c918`
- `0x180131c10`

## callees

- `0x1800e5a90`
- `0x1800e5cd0`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800e5b69`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800e5b69`
- `ntdll!RtlReleaseRelativeName` at `0x1800e5c0e`
- `ntdll!RtlReleaseRelativeName` at `0x1800e5c0e`
- `ntdll!RtlNtStatusToDosError` at `0x1800e5c86`
- `ntdll!RtlNtStatusToDosError` at `0x1800e5c86`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e5b0f`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e5b0f`
- `ntdll!NtLoadKeyEx` at `0x1800e5bfb`
- `ntdll!NtLoadKeyEx` at `0x1800e5bfb`
- `ntdll!RtlFreeHeap` at `0x1800e5c39`
- `ntdll!RtlFreeHeap` at `0x1800e5c5c`
- `ntdll!RtlFreeHeap` at `0x1800e5c39`
- `ntdll!RtlFreeHeap` at `0x1800e5c5c`

## pseudocode

```c

```
