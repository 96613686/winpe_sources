# GetLongPathNameW

- ea: `0x180082020`
- end: `0x1800827cf`
- name: `GetLongPathNameW`
- size: `1967`
- prototype: `DWORD __stdcall(LPCWSTR lpszShortPath, LPWSTR lpszLongPath, DWORD cchBuffer)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180083ac0`
- `0x1801477a0`

## callees

- `0x18004e3d0`
- `0x180082020`
- `0x180082860`
- `0x180082f80`
- `0x180083140`
- `0x1800832d0`
- `0x1801369c9`
- `0x18013877c`
- `0x180194ec5`
- `0x180194f10`

## import_xrefs

- `ntdll!wcslen` at `0x18008222a`
- `ntdll!wcslen` at `0x180082457`
- `ntdll!wcslen` at `0x18008264a`
- `ntdll!wcslen` at `0x1800826ff`
- `ntdll!wcslen` at `0x18008222a`
- `ntdll!wcslen` at `0x180082457`
- `ntdll!wcslen` at `0x18008264a`
- `ntdll!wcslen` at `0x1800826ff`
- `ntdll!RtlSetLastWin32Error` at `0x180082510`
- `ntdll!RtlSetLastWin32Error` at `0x18008269d`
- `ntdll!RtlSetLastWin32Error` at `0x1800827bf`
- `ntdll!RtlSetLastWin32Error` at `0x180082510`
- `ntdll!RtlSetLastWin32Error` at `0x18008269d`
- `ntdll!RtlSetLastWin32Error` at `0x1800827bf`
- `ntdll!RtlFreeHeap` at `0x18008275b`
- `ntdll!RtlFreeHeap` at `0x18008277e`
- `ntdll!RtlFreeHeap` at `0x180195914`
- `ntdll!RtlFreeHeap` at `0x180195939`
- `ntdll!RtlFreeHeap` at `0x18008275b`
- `ntdll!RtlFreeHeap` at `0x18008277e`
- `ntdll!RtlFreeHeap` at `0x180195914`
- `ntdll!RtlFreeHeap` at `0x180195939`
- `ntdll!RtlAllocateHeap` at `0x1800824f5`
- `ntdll!RtlAllocateHeap` at `0x180082678`
- `ntdll!RtlAllocateHeap` at `0x1800824f5`
- `ntdll!RtlAllocateHeap` at `0x180082678`

## pseudocode

```c

```
