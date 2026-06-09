# ConvertUserStringToSidString(ushort const *,ushort * *)

- ea: `0x1801e6280`
- end: `0x1801e665c`
- name: `?ConvertUserStringToSidString@@YA_NPEBGPEAPEAG@Z`
- size: `988`
- prototype: `bool __fastcall(const unsigned __int16 *, LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800d8aa4`

## callees

- `0x18000c4bc`
- `0x1801e6280`

## import_xrefs

- `ADVAPI32!LookupAccountNameW` at `0x1801e6458`
- `ADVAPI32!LookupAccountNameW` at `0x1801e6579`
- `ADVAPI32!LookupAccountNameW` at `0x1801e6458`
- `ADVAPI32!LookupAccountNameW` at `0x1801e6579`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1801e65ee`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1801e65ee`
- `KERNEL32!HeapReAlloc` at `0x1801e64a0`
- `KERNEL32!HeapReAlloc` at `0x1801e6532`
- `KERNEL32!HeapReAlloc` at `0x1801e64a0`
- `KERNEL32!HeapReAlloc` at `0x1801e6532`
- `KERNEL32!GetProcessHeap` at `0x1801e6305`
- `KERNEL32!GetProcessHeap` at `0x1801e6393`
- `KERNEL32!GetProcessHeap` at `0x1801e6488`
- `KERNEL32!GetProcessHeap` at `0x1801e651a`
- `KERNEL32!GetProcessHeap` at `0x1801e6605`
- `KERNEL32!GetProcessHeap` at `0x1801e662a`
- `KERNEL32!GetProcessHeap` at `0x1801e6305`
- `KERNEL32!GetProcessHeap` at `0x1801e6393`
- `KERNEL32!GetProcessHeap` at `0x1801e6488`
- `KERNEL32!GetProcessHeap` at `0x1801e651a`
- `KERNEL32!GetProcessHeap` at `0x1801e6605`
- `KERNEL32!GetProcessHeap` at `0x1801e662a`
- `KERNEL32!HeapAlloc` at `0x1801e631e`
- `KERNEL32!HeapAlloc` at `0x1801e63ab`
- `KERNEL32!HeapAlloc` at `0x1801e631e`
- `KERNEL32!HeapAlloc` at `0x1801e63ab`
- `KERNEL32!HeapFree` at `0x1801e6619`
- `KERNEL32!HeapFree` at `0x1801e663e`
- `KERNEL32!HeapFree` at `0x1801e6619`
- `KERNEL32!HeapFree` at `0x1801e663e`
- `KERNEL32!GetLastError` at `0x1801e633f`
- `KERNEL32!GetLastError` at `0x1801e63c8`
- `KERNEL32!GetLastError` at `0x1801e646c`
- `KERNEL32!GetLastError` at `0x1801e64be`
- `KERNEL32!GetLastError` at `0x1801e6592`
- `KERNEL32!GetLastError` at `0x1801e633f`
- `KERNEL32!GetLastError` at `0x1801e63c8`
- `KERNEL32!GetLastError` at `0x1801e646c`
- `KERNEL32!GetLastError` at `0x1801e64be`
- `KERNEL32!GetLastError` at `0x1801e6592`

## string_xrefs

- `0x1801e62c5`: `Error. Username is null. Cannot retrieve SID.`
- `0x1801e65af`: `Error: %d. Failed to lookup SID corresponding to account %s`

## pseudocode

```c

```
