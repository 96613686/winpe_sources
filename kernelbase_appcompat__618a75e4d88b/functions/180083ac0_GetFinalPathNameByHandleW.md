# GetFinalPathNameByHandleW

- ea: `0x180083ac0`
- end: `0x1800843f7`
- name: `GetFinalPathNameByHandleW`
- size: `2359`
- prototype: `DWORD __stdcall(HANDLE hFile, LPWSTR lpszFilePath, DWORD cchFilePath, DWORD dwFlags)`
- caller_count: `5`
- callee_count: `8`
- tags: `reparse_path, loader_planting`

## callers

- `0x180052e40`
- `0x180084ad0`
- `0x180116258`
- `0x18015ba60`
- `0x18018d67c`

## callees

- `0x18004b9d0`
- `0x180078a10`
- `0x18007cf00`
- `0x180082020`
- `0x180083ac0`
- `0x180084400`
- `0x180084750`
- `0x180194ec5`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180083ca8`
- `ntdll!NtQueryInformationFile` at `0x180083fa9`
- `ntdll!NtQueryInformationFile` at `0x180083ca8`
- `ntdll!NtQueryInformationFile` at `0x180083fa9`
- `ntdll!wcslen` at `0x180083cf8`
- `ntdll!wcslen` at `0x180083d0a`
- `ntdll!wcslen` at `0x180083d24`
- `ntdll!wcslen` at `0x180083d36`
- `ntdll!wcslen` at `0x180083d83`
- `ntdll!wcslen` at `0x180083d95`
- `ntdll!wcslen` at `0x18008415f`
- `ntdll!wcslen` at `0x180084171`
- `ntdll!wcslen` at `0x180084211`
- `ntdll!wcslen` at `0x180084222`
- `ntdll!wcslen` at `0x1800843ad`
- `ntdll!wcslen` at `0x1800843cc`
- `ntdll!wcslen` at `0x180083cf8`
- `ntdll!wcslen` at `0x180083d0a`
- `ntdll!wcslen` at `0x180083d24`
- `ntdll!wcslen` at `0x180083d36`
- `ntdll!wcslen` at `0x180083d83`
- `ntdll!wcslen` at `0x180083d95`
- `ntdll!wcslen` at `0x18008415f`
- `ntdll!wcslen` at `0x180084171`
- `ntdll!wcslen` at `0x180084211`
- `ntdll!wcslen` at `0x180084222`
- `ntdll!wcslen` at `0x1800843ad`
- `ntdll!wcslen` at `0x1800843cc`
- `ntdll!RtlSetLastWin32Error` at `0x180084050`
- `ntdll!RtlSetLastWin32Error` at `0x180084096`
- `ntdll!RtlSetLastWin32Error` at `0x180084290`
- `ntdll!RtlSetLastWin32Error` at `0x1800842a9`
- `ntdll!RtlSetLastWin32Error` at `0x1800842fe`
- `ntdll!RtlSetLastWin32Error` at `0x180084314`
- `ntdll!RtlSetLastWin32Error` at `0x18019db40`
- `ntdll!RtlSetLastWin32Error` at `0x18019dbfa`
- `ntdll!RtlSetLastWin32Error` at `0x180084050`
- `ntdll!RtlSetLastWin32Error` at `0x180084096`
- `ntdll!RtlSetLastWin32Error` at `0x180084290`
- `ntdll!RtlSetLastWin32Error` at `0x1800842a9`
- `ntdll!RtlSetLastWin32Error` at `0x1800842fe`
- `ntdll!RtlSetLastWin32Error` at `0x180084314`
- `ntdll!RtlSetLastWin32Error` at `0x18019db40`
- `ntdll!RtlSetLastWin32Error` at `0x18019dbfa`
- `ntdll!RtlFreeHeap` at `0x180083b90`
- `ntdll!RtlFreeHeap` at `0x180083c58`
- `ntdll!RtlFreeHeap` at `0x180083ead`
- `ntdll!RtlFreeHeap` at `0x180083ed5`
- `ntdll!RtlFreeHeap` at `0x180083ef8`
- `ntdll!RtlFreeHeap` at `0x180083f59`
- `ntdll!RtlFreeHeap` at `0x180083ff9`
- `ntdll!RtlFreeHeap` at `0x1800840d8`
- `ntdll!RtlFreeHeap` at `0x180084113`
- `ntdll!RtlFreeHeap` at `0x180084264`
- `ntdll!RtlFreeHeap` at `0x1800842df`
- `ntdll!RtlFreeHeap` at `0x18008438f`
- `ntdll!RtlFreeHeap` at `0x18019db6f`
- `ntdll!RtlFreeHeap` at `0x18019db92`
- `ntdll!RtlFreeHeap` at `0x18019dbc5`
- `ntdll!RtlFreeHeap` at `0x18019dbec`
- `ntdll!RtlFreeHeap` at `0x180083b90`
- `ntdll!RtlFreeHeap` at `0x180083c58`
- `ntdll!RtlFreeHeap` at `0x180083ead`
- `ntdll!RtlFreeHeap` at `0x180083ed5`
- `ntdll!RtlFreeHeap` at `0x180083ef8`
- `ntdll!RtlFreeHeap` at `0x180083f59`
- `ntdll!RtlFreeHeap` at `0x180083ff9`
- `ntdll!RtlFreeHeap` at `0x1800840d8`
- `ntdll!RtlFreeHeap` at `0x180084113`
- `ntdll!RtlFreeHeap` at `0x180084264`
- `ntdll!RtlFreeHeap` at `0x1800842df`
- `ntdll!RtlFreeHeap` at `0x18008438f`
- `ntdll!RtlFreeHeap` at `0x18019db6f`
- `ntdll!RtlFreeHeap` at `0x18019db92`
- `ntdll!RtlFreeHeap` at `0x18019dbc5`
- `ntdll!RtlFreeHeap` at `0x18019dbec`
- `ntdll!NtQueryObject` at `0x180083be7`
- `ntdll!NtQueryObject` at `0x180083be7`
- `ntdll!RtlAllocateHeap` at `0x180083bb2`
- `ntdll!RtlAllocateHeap` at `0x180083c7a`
- `ntdll!RtlAllocateHeap` at `0x180083f7b`
- `ntdll!RtlAllocateHeap` at `0x1800841a1`
- `ntdll!RtlAllocateHeap` at `0x180083bb2`
- `ntdll!RtlAllocateHeap` at `0x180083c7a`
- `ntdll!RtlAllocateHeap` at `0x180083f7b`
- `ntdll!RtlAllocateHeap` at `0x1800841a1`

## pseudocode

```c

```
