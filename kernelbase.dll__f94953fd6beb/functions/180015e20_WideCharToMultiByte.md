# WideCharToMultiByte

- ea: `0x180015e20`
- end: `0x1800175f9`
- name: `WideCharToMultiByte`
- size: `6105`
- prototype: `int __stdcall(UINT CodePage, DWORD dwFlags, LPCWCH lpWideCharStr, int cchWideChar, LPSTR lpMultiByteStr, int cbMultiByte, LPCCH lpDefaultChar, LPBOOL lpUsedDefaultChar)`
- caller_count: `18`
- callee_count: `22`
- tags: `registry_config, loader_planting`

## callers

- `0x1800036a0`
- `0x180006dac`
- `0x180009c80`
- `0x18001fc50`
- `0x18003e120`
- `0x18003fa10`
- `0x1800543b8`
- `0x180074acc`
- `0x1800ad410`
- `0x1800ad720`
- `0x1800ddbf0`
- `0x1800e3080`
- `0x1800f26c0`
- `0x180137d24`
- `0x18013dc00`
- `0x180140a80`
- `0x180140e00`
- `0x180173680`

## callees

- `0x1800108d0`
- `0x1800145c0`
- `0x1800147a0`
- `0x180015d70`
- `0x180015e20`
- `0x180017600`
- `0x180017950`
- `0x1800181e0`
- `0x18001b3a0`
- `0x18001ea10`
- `0x1800222a0`
- `0x180037714`
- `0x18003ab50`
- `0x18003b5e8`
- `0x18003e054`
- `0x180087e94`
- `0x1800bf6e0`
- `0x1801249d4`
- `0x180127494`
- `0x18012d119`
- `0x180188f10`
- `0x180197010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800161be`
- `ntdll!RtlInitUnicodeString` at `0x1800169e0`
- `ntdll!RtlInitUnicodeString` at `0x180016a76`
- `ntdll!RtlInitUnicodeString` at `0x1800161be`
- `ntdll!RtlInitUnicodeString` at `0x1800169e0`
- `ntdll!RtlInitUnicodeString` at `0x180016a76`
- `ntdll!NtOpenKey` at `0x1800161f4`
- `ntdll!NtOpenKey` at `0x1800161f4`
- `ntdll!NtQueryValueKey` at `0x180016a1a`
- `ntdll!NtQueryValueKey` at `0x180016a1a`
- `ntdll!RtlUnicodeStringToInteger` at `0x180016a8a`
- `ntdll!RtlUnicodeStringToInteger` at `0x180016a8a`
- `ntdll!NtGetNlsSectionPtr` at `0x180016c9c`
- `ntdll!NtGetNlsSectionPtr` at `0x180016e10`
- `ntdll!NtGetNlsSectionPtr` at `0x180016c9c`
- `ntdll!NtGetNlsSectionPtr` at `0x180016e10`
- `ntdll!RtlUnicodeToUTF8N` at `0x180016074`
- `ntdll!RtlUnicodeToUTF8N` at `0x180016074`
- `ntdll!NtClose` at `0x1800169b7`
- `ntdll!NtClose` at `0x1800169b7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016958`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016b33`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016cd5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016d88`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016fa8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016958`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016b33`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016cd5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016d88`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016fa8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016983`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016b5d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016cb3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016cfc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016dc9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016e27`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016fcd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016983`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016b5d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016cb3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016cfc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016dc9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016e27`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016fcd`
- `ntdll!RtlFreeHeap` at `0x180016400`
- `ntdll!RtlFreeHeap` at `0x180016400`
- `ntdll!RtlAllocateHeap` at `0x18001623a`
- `ntdll!RtlAllocateHeap` at `0x180016db2`
- `ntdll!RtlAllocateHeap` at `0x180016eea`
- `ntdll!RtlAllocateHeap` at `0x180017010`
- `ntdll!RtlAllocateHeap` at `0x18001623a`
- `ntdll!RtlAllocateHeap` at `0x180016db2`
- `ntdll!RtlAllocateHeap` at `0x180016eea`
- `ntdll!RtlAllocateHeap` at `0x180017010`

## string_xrefs

- `0x180016857`: `\Registry\Machine\System\CurrentControlSet\Control`
- `0x1800173d1`: `NlsDllCodePageTranslation`
- `0x1800174e7`: `NlsDllCodePageTranslation`

## pseudocode

```c

```
