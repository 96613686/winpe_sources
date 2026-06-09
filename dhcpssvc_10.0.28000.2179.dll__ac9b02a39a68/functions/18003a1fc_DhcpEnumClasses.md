# DhcpEnumClasses

- ea: `0x18003a1fc`
- end: `0x18003a46d`
- name: `DhcpEnumClasses`
- size: `625`
- prototype: `DWORD __stdcall(LPWSTR ServerIpAddress, DWORD ReservedMustBeZero, DHCP_RESUME_HANDLE *ResumeHandle, DWORD PreferredMaximum, LPDHCP_CLASS_INFO_ARRAY *ClassInfoArray, DWORD *nRead, DWORD *nTotal)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180041c00`

## callees

- `0x180038210`
- `0x18003a1fc`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18003a28b`
- `KERNEL32!LocalAlloc` at `0x18003a2b8`
- `KERNEL32!LocalAlloc` at `0x18003a28b`
- `KERNEL32!LocalAlloc` at `0x18003a2b8`
- `KERNEL32!LocalFree` at `0x18003a2cf`
- `KERNEL32!LocalFree` at `0x18003a39e`
- `KERNEL32!LocalFree` at `0x18003a3b4`
- `KERNEL32!LocalFree` at `0x18003a3ca`
- `KERNEL32!LocalFree` at `0x18003a3f7`
- `KERNEL32!LocalFree` at `0x18003a40c`
- `KERNEL32!LocalFree` at `0x18003a420`
- `KERNEL32!LocalFree` at `0x18003a435`
- `KERNEL32!LocalFree` at `0x18003a444`
- `KERNEL32!LocalFree` at `0x18003a2cf`
- `KERNEL32!LocalFree` at `0x18003a39e`
- `KERNEL32!LocalFree` at `0x18003a3b4`
- `KERNEL32!LocalFree` at `0x18003a3ca`
- `KERNEL32!LocalFree` at `0x18003a3f7`
- `KERNEL32!LocalFree` at `0x18003a40c`
- `KERNEL32!LocalFree` at `0x18003a420`
- `KERNEL32!LocalFree` at `0x18003a435`
- `KERNEL32!LocalFree` at `0x18003a444`

## pseudocode

```c

```
