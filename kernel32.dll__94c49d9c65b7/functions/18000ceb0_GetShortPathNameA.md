# GetShortPathNameA

- ea: `0x18000ceb0`
- end: `0x18000d0b5`
- name: `GetShortPathNameA`
- size: `517`
- prototype: `DWORD __stdcall(LPCSTR lpszLongPath, LPSTR lpszShortPath, DWORD cchBuffer)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000c110`
- `0x18000ceb0`
- `0x18000d6c0`
- `0x18000f920`
- `0x18005c390`
- `0x18007a840`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlFreeAnsiString` at `0x18000d03f`
- `ntdll!RtlFreeAnsiString` at `0x18007ac28`
- `ntdll!RtlFreeAnsiString` at `0x18000d03f`
- `ntdll!RtlFreeAnsiString` at `0x18007ac28`
- `ntdll!RtlFreeUnicodeString` at `0x18000d084`
- `ntdll!RtlFreeUnicodeString` at `0x18007ac16`
- `ntdll!RtlFreeUnicodeString` at `0x18000d084`
- `ntdll!RtlFreeUnicodeString` at `0x18007ac16`
- `ntdll!RtlSetLastWin32Error` at `0x18000d01b`
- `ntdll!RtlSetLastWin32Error` at `0x18000d091`
- `ntdll!RtlSetLastWin32Error` at `0x18000d01b`
- `ntdll!RtlSetLastWin32Error` at `0x18000d091`
- `ntdll!RtlFreeHeap` at `0x18000d0ad`
- `ntdll!RtlFreeHeap` at `0x18007ac50`
- `ntdll!RtlFreeHeap` at `0x18000d0ad`
- `ntdll!RtlFreeHeap` at `0x18007ac50`
- `ntdll!RtlAllocateHeap` at `0x18000cfdd`
- `ntdll!RtlAllocateHeap` at `0x18000cfdd`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000cfbc`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000cfbc`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18000cf6e`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18000cf6e`

## pseudocode

```c

```
