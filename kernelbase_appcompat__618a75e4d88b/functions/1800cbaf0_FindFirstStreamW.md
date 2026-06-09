# FindFirstStreamW

- ea: `0x1800cbaf0`
- end: `0x1800cbe37`
- name: `FindFirstStreamW`
- size: `839`
- prototype: `HANDLE __stdcall(LPCWSTR lpFileName, STREAM_INFO_LEVELS InfoLevel, LPVOID lpFindStreamData, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting`

## callees

- `0x18004b9d0`
- `0x180082f80`
- `0x1800cbaf0`
- `0x1800cbe40`
- `0x180194eb9`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x1800cbcac`
- `ntdll!NtQueryInformationFile` at `0x1800cbcac`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800cbb4e`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800cbb4e`
- `ntdll!NtCreateFile` at `0x1800cbbfe`
- `ntdll!NtCreateFile` at `0x1800cbbfe`
- `ntdll!RtlSetLastWin32Error` at `0x1801a0a08`
- `ntdll!RtlSetLastWin32Error` at `0x1801a0a08`
- `ntdll!NtClose` at `0x1800cbe1f`
- `ntdll!NtClose` at `0x180197630`
- `ntdll!NtClose` at `0x1800cbe1f`
- `ntdll!NtClose` at `0x180197630`
- `ntdll!RtlFreeHeap` at `0x1800cbc5b`
- `ntdll!RtlFreeHeap` at `0x1800cbd94`
- `ntdll!RtlFreeHeap` at `0x1800cbe07`
- `ntdll!RtlFreeHeap` at `0x18019760b`
- `ntdll!RtlFreeHeap` at `0x180197655`
- `ntdll!RtlFreeHeap` at `0x1800cbc5b`
- `ntdll!RtlFreeHeap` at `0x1800cbd94`
- `ntdll!RtlFreeHeap` at `0x1800cbe07`
- `ntdll!RtlFreeHeap` at `0x18019760b`
- `ntdll!RtlFreeHeap` at `0x180197655`
- `ntdll!RtlAllocateHeap` at `0x1800cbc79`
- `ntdll!RtlAllocateHeap` at `0x1800cbc79`

## pseudocode

```c

```
