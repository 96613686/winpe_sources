# CreateDirectoryAndGetHandle(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,_SECURITY_ATTRIBUTES const *,void * *,ulong,ulong)

- ea: `0x18009c4b0`
- end: `0x18009c6b6`
- name: `?CreateDirectoryAndGetHandle@@YAHV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEBU_SECURITY_ATTRIBUTES@@PEAPEAXKK@Z`
- size: `518`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18009bca0`
- `0x18009c1dc`
- `0x1802b95cc`

## callees

- `0x18002be90`
- `0x18002df00`
- `0x18009c4b0`
- `0x18020aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009c623`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009c623`
- `ntdll!RtlFreeHeap` at `0x18009c5fc`
- `ntdll!RtlFreeHeap` at `0x18009c5fc`
- `ntdll!RtlReleaseRelativeName` at `0x18009c5e4`
- `ntdll!RtlReleaseRelativeName` at `0x18009c5e4`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18009c53c`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18009c53c`
- `ntdll!NtCreateFile` at `0x18009c5d7`
- `ntdll!NtCreateFile` at `0x18009c5d7`
- `ntdll!NtClose` at `0x18009c6ab`
- `ntdll!NtClose` at `0x18009c6ab`
- `ntdll!RtlNtStatusToDosError` at `0x18009c673`
- `ntdll!RtlNtStatusToDosError` at `0x18009c673`
- `ntdll!RtlIsDosDeviceName_U` at `0x18009c661`
- `ntdll!RtlIsDosDeviceName_U` at `0x18009c661`

## pseudocode

```c

```
