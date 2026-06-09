# MultiByteToWideChar

- ea: `0x18001e3e0`
- end: `0x18001ffe0`
- name: `MultiByteToWideChar`
- size: `7168`
- prototype: `int __stdcall(UINT CodePage, DWORD dwFlags, LPCCH lpMultiByteStr, int cbMultiByte, LPWSTR lpWideCharStr, int cchWideChar)`
- caller_count: `20`
- callee_count: `19`
- tags: `registry_config, loader_planting`

## callers

- `0x18001cd50`
- `0x18001fff0`
- `0x1800202d0`
- `0x1800348e0`
- `0x180039ab0`
- `0x180040114`
- `0x1800410f0`
- `0x1800418a0`
- `0x180078a90`
- `0x1800a6a20`
- `0x1800b6b10`
- `0x1800eea40`
- `0x1800eeac0`
- `0x1800f3f10`
- `0x18013cbd0`
- `0x18013e0e0`
- `0x18013e180`
- `0x18013e240`
- `0x18013e2e0`
- `0x180141ae0`

## callees

- `0x18001cd34`
- `0x18001e3e0`
- `0x180020170`
- `0x180020244`
- `0x180020ad0`
- `0x180021e08`
- `0x180024ed0`
- `0x1800285f0`
- `0x180028630`
- `0x1800393f0`
- `0x180048f20`
- `0x18004cc30`
- `0x18004ce20`
- `0x18004e3d0`
- `0x18012dfb4`
- `0x180130d10`
- `0x1801369c9`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001f1b6`
- `ntdll!RtlInitUnicodeString` at `0x18001f465`
- `ntdll!RtlInitUnicodeString` at `0x18001f50c`
- `ntdll!RtlInitUnicodeString` at `0x18001f1b6`
- `ntdll!RtlInitUnicodeString` at `0x18001f465`
- `ntdll!RtlInitUnicodeString` at `0x18001f50c`
- `ntdll!NtOpenKey` at `0x18001f1f6`
- `ntdll!NtOpenKey` at `0x18001f1f6`
- `ntdll!NtQueryValueKey` at `0x18001f4a6`
- `ntdll!NtQueryValueKey` at `0x18001f4a6`
- `ntdll!RtlUnicodeStringToInteger` at `0x18001f526`
- `ntdll!RtlUnicodeStringToInteger` at `0x18001f526`
- `ntdll!NtGetNlsSectionPtr` at `0x18001f77d`
- `ntdll!NtGetNlsSectionPtr` at `0x18001f832`
- `ntdll!NtGetNlsSectionPtr` at `0x18001f77d`
- `ntdll!NtGetNlsSectionPtr` at `0x18001f832`
- `ntdll!RtlUTF8ToUnicodeN` at `0x18001e65a`
- `ntdll!RtlUTF8ToUnicodeN` at `0x18001e65a`
- `ntdll!NtClose` at `0x18001f42e`
- `ntdll!NtClose` at `0x18001f42e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001f3c4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001f5dd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001f7c2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001f8e2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001fadb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001fc50`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001f3c4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001f5dd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001f7c2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001f8e2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001fadb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001fc50`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001f3f4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001f60d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001f79a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001f7ef`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001f84f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001f92f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001fb06`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001fc7a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001f3f4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001f60d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001f79a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001f7ef`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001f84f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001f92f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001fb06`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001fc7a`
- `ntdll!RtlAllocateHeap` at `0x18001f912`
- `ntdll!RtlAllocateHeap` at `0x18001fa0d`
- `ntdll!RtlAllocateHeap` at `0x18001fb5d`
- `ntdll!RtlAllocateHeap` at `0x18001f912`
- `ntdll!RtlAllocateHeap` at `0x18001fa0d`
- `ntdll!RtlAllocateHeap` at `0x18001fb5d`

## string_xrefs

- `0x18001f2dd`: `\Registry\Machine\System\CurrentControlSet\Control`
- `0x18001fdb4`: `NlsDllCodePageTranslation`
- `0x18001fed1`: `NlsDllCodePageTranslation`

## pseudocode

```c

```
