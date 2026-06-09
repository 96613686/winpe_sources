# GetShortPathNameW

- ea: `0x180081780`
- end: `0x180081c62`
- name: `GetShortPathNameW`
- size: `1250`
- prototype: `DWORD __stdcall(LPCWSTR lpszLongPath, LPWSTR lpszShortPath, DWORD cchBuffer)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x18004e3d0`
- `0x18007caa0`
- `0x180081780`
- `0x180081c70`
- `0x180082860`
- `0x180082f80`
- `0x180083140`
- `0x1800832d0`
- `0x1801369c9`
- `0x18013877c`
- `0x180194ec5`
- `0x180194f10`

## import_xrefs

- `ntdll!wcslen` at `0x180081840`
- `ntdll!wcslen` at `0x18008188b`
- `ntdll!wcslen` at `0x1800819db`
- `ntdll!wcslen` at `0x180081a65`
- `ntdll!wcslen` at `0x180081840`
- `ntdll!wcslen` at `0x18008188b`
- `ntdll!wcslen` at `0x1800819db`
- `ntdll!wcslen` at `0x180081a65`
- `ntdll!RtlSetLastWin32Error` at `0x1800818dd`
- `ntdll!RtlSetLastWin32Error` at `0x180081b49`
- `ntdll!RtlSetLastWin32Error` at `0x180081c2f`
- `ntdll!RtlSetLastWin32Error` at `0x1800818dd`
- `ntdll!RtlSetLastWin32Error` at `0x180081b49`
- `ntdll!RtlSetLastWin32Error` at `0x180081c2f`
- `ntdll!RtlFreeHeap` at `0x180081bf0`
- `ntdll!RtlFreeHeap` at `0x180081c51`
- `ntdll!RtlFreeHeap` at `0x18019589f`
- `ntdll!RtlFreeHeap` at `0x1801958c4`
- `ntdll!RtlFreeHeap` at `0x180081bf0`
- `ntdll!RtlFreeHeap` at `0x180081c51`
- `ntdll!RtlFreeHeap` at `0x18019589f`
- `ntdll!RtlFreeHeap` at `0x1801958c4`
- `ntdll!RtlAllocateHeap` at `0x1800818be`
- `ntdll!RtlAllocateHeap` at `0x180081b2a`
- `ntdll!RtlAllocateHeap` at `0x1800818be`
- `ntdll!RtlAllocateHeap` at `0x180081b2a`

## pseudocode

```c

```
