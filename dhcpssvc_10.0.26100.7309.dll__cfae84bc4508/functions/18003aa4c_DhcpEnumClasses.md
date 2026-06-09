# DhcpEnumClasses

- ea: `0x18003aa4c`
- end: `0x18003acb5`
- name: `DhcpEnumClasses`
- size: `617`
- prototype: `DWORD __stdcall(LPWSTR ServerIpAddress, DWORD ReservedMustBeZero, DHCP_RESUME_HANDLE *ResumeHandle, DWORD PreferredMaximum, LPDHCP_CLASS_INFO_ARRAY *ClassInfoArray, DWORD *nRead, DWORD *nTotal)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180042100`

## callees

- `0x180038b40`
- `0x18003aa4c`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18003aad6`
- `KERNEL32!LocalAlloc` at `0x18003ab03`
- `KERNEL32!LocalAlloc` at `0x18003aad6`
- `KERNEL32!LocalAlloc` at `0x18003ab03`
- `KERNEL32!LocalFree` at `0x18003abe4`
- `KERNEL32!LocalFree` at `0x18003abfa`
- `KERNEL32!LocalFree` at `0x18003ac10`
- `KERNEL32!LocalFree` at `0x18003ac3f`
- `KERNEL32!LocalFree` at `0x18003ac54`
- `KERNEL32!LocalFree` at `0x18003ac68`
- `KERNEL32!LocalFree` at `0x18003ac7f`
- `KERNEL32!LocalFree` at `0x18003ac8e`
- `KERNEL32!LocalFree` at `0x18003abe4`
- `KERNEL32!LocalFree` at `0x18003abfa`
- `KERNEL32!LocalFree` at `0x18003ac10`
- `KERNEL32!LocalFree` at `0x18003ac3f`
- `KERNEL32!LocalFree` at `0x18003ac54`
- `KERNEL32!LocalFree` at `0x18003ac68`
- `KERNEL32!LocalFree` at `0x18003ac7f`
- `KERNEL32!LocalFree` at `0x18003ac8e`

## pseudocode

```c

```
