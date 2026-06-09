# ConvertUserStringToSidString(ushort const *,ushort * *)

- ea: `0x1801dd424`
- end: `0x1801dd783`
- name: `?ConvertUserStringToSidString@@YA_NPEBGPEAPEAG@Z`
- size: `863`
- prototype: `bool __fastcall(const unsigned __int16 *, LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180132d38`

## callees

- `0x180025a18`
- `0x1801dd424`

## import_xrefs

- `ADVAPI32!LookupAccountNameW` at `0x1801dd5d8`
- `ADVAPI32!LookupAccountNameW` at `0x1801dd6cb`
- `ADVAPI32!LookupAccountNameW` at `0x1801dd5d8`
- `ADVAPI32!LookupAccountNameW` at `0x1801dd6cb`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1801dd734`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1801dd734`
- `KERNEL32!HeapReAlloc` at `0x1801dd60e`
- `KERNEL32!HeapReAlloc` at `0x1801dd68e`
- `KERNEL32!HeapReAlloc` at `0x1801dd60e`
- `KERNEL32!HeapReAlloc` at `0x1801dd68e`
- `KERNEL32!GetProcessHeap` at `0x1801dd4a9`
- `KERNEL32!GetProcessHeap` at `0x1801dd525`
- `KERNEL32!GetProcessHeap` at `0x1801dd5fc`
- `KERNEL32!GetProcessHeap` at `0x1801dd67c`
- `KERNEL32!GetProcessHeap` at `0x1801dd745`
- `KERNEL32!GetProcessHeap` at `0x1801dd75e`
- `KERNEL32!GetProcessHeap` at `0x1801dd4a9`
- `KERNEL32!GetProcessHeap` at `0x1801dd525`
- `KERNEL32!GetProcessHeap` at `0x1801dd5fc`
- `KERNEL32!GetProcessHeap` at `0x1801dd67c`
- `KERNEL32!GetProcessHeap` at `0x1801dd745`
- `KERNEL32!GetProcessHeap` at `0x1801dd75e`
- `KERNEL32!HeapAlloc` at `0x1801dd4bc`
- `KERNEL32!HeapAlloc` at `0x1801dd537`
- `KERNEL32!HeapAlloc` at `0x1801dd4bc`
- `KERNEL32!HeapAlloc` at `0x1801dd537`
- `KERNEL32!HeapFree` at `0x1801dd753`
- `KERNEL32!HeapFree` at `0x1801dd76c`
- `KERNEL32!HeapFree` at `0x1801dd753`
- `KERNEL32!HeapFree` at `0x1801dd76c`
- `KERNEL32!GetLastError` at `0x1801dd4d7`
- `KERNEL32!GetLastError` at `0x1801dd54e`
- `KERNEL32!GetLastError` at `0x1801dd5e6`
- `KERNEL32!GetLastError` at `0x1801dd626`
- `KERNEL32!GetLastError` at `0x1801dd6de`
- `KERNEL32!GetLastError` at `0x1801dd4d7`
- `KERNEL32!GetLastError` at `0x1801dd54e`
- `KERNEL32!GetLastError` at `0x1801dd5e6`
- `KERNEL32!GetLastError` at `0x1801dd626`
- `KERNEL32!GetLastError` at `0x1801dd6de`

## string_xrefs

- `0x1801dd469`: `Error. Username is null. Cannot retrieve SID.`
- `0x1801dd6f5`: `Error: %d. Failed to lookup SID corresponding to account %s`

## pseudocode

```c

```
