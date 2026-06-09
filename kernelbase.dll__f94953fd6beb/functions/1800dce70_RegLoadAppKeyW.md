# RegLoadAppKeyW

- ea: `0x1800dce70`
- end: `0x1800dd07d`
- name: `RegLoadAppKeyW`
- size: `525`
- prototype: `LSTATUS __stdcall(LPCWSTR lpFile, PHKEY phkResult, REGSAM samDesired, DWORD dwOptions, DWORD Reserved)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x18011328c`
- `0x180128380`

## callees

- `0x1800dce70`
- `0x1800dd084`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800dcf43`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800dcf43`
- `ntdll!RtlReleaseRelativeName` at `0x1800dcfdc`
- `ntdll!RtlReleaseRelativeName` at `0x1800dcfdc`
- `ntdll!RtlNtStatusToDosError` at `0x1800dd041`
- `ntdll!RtlNtStatusToDosError` at `0x1800dd041`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800dceef`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800dceef`
- `ntdll!NtLoadKeyEx` at `0x1800dcfcf`
- `ntdll!NtLoadKeyEx` at `0x1800dcfcf`
- `ntdll!RtlFreeHeap` at `0x1800dd001`
- `ntdll!RtlFreeHeap` at `0x1800dd01e`
- `ntdll!RtlFreeHeap` at `0x1800dd001`
- `ntdll!RtlFreeHeap` at `0x1800dd01e`

## pseudocode

```c

```
