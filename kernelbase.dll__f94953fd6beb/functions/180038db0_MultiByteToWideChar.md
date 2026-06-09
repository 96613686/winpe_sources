# MultiByteToWideChar

- ea: `0x180038db0`
- end: `0x18003a908`
- name: `MultiByteToWideChar`
- size: `7000`
- prototype: `int __stdcall(UINT CodePage, DWORD dwFlags, LPCCH lpMultiByteStr, int cbMultiByte, LPWSTR lpWideCharStr, int cchWideChar)`
- caller_count: `20`
- callee_count: `19`
- tags: `registry_config, loader_planting`

## callers

- `0x180005f14`
- `0x180006e80`
- `0x180007610`
- `0x180008db0`
- `0x180022940`
- `0x180037730`
- `0x18003a910`
- `0x18003abc0`
- `0x18003b620`
- `0x18003e120`
- `0x180095240`
- `0x1800e6750`
- `0x1800e67d0`
- `0x1800eb760`
- `0x180133170`
- `0x180134570`
- `0x180134610`
- `0x1801346d0`
- `0x180134770`
- `0x180137e90`

## callees

- `0x1800108d0`
- `0x1800145c0`
- `0x1800147a0`
- `0x180015d70`
- `0x1800181e0`
- `0x18001b3a0`
- `0x18001ea10`
- `0x1800222a0`
- `0x180037714`
- `0x180038db0`
- `0x18003aa80`
- `0x18003ab50`
- `0x18003b5e8`
- `0x18003e054`
- `0x1801249d4`
- `0x180127494`
- `0x18012d119`
- `0x180188f10`
- `0x180197010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180039b82`
- `ntdll!RtlInitUnicodeString` at `0x180039e13`
- `ntdll!RtlInitUnicodeString` at `0x180039eae`
- `ntdll!RtlInitUnicodeString` at `0x180039b82`
- `ntdll!RtlInitUnicodeString` at `0x180039e13`
- `ntdll!RtlInitUnicodeString` at `0x180039eae`
- `ntdll!NtOpenKey` at `0x180039bbc`
- `ntdll!NtOpenKey` at `0x180039bbc`
- `ntdll!NtQueryValueKey` at `0x180039e4e`
- `ntdll!NtQueryValueKey` at `0x180039e4e`
- `ntdll!RtlUnicodeStringToInteger` at `0x180039ec2`
- `ntdll!RtlUnicodeStringToInteger` at `0x180039ec2`
- `ntdll!NtGetNlsSectionPtr` at `0x18003a10d`
- `ntdll!NtGetNlsSectionPtr` at `0x18003a1aa`
- `ntdll!NtGetNlsSectionPtr` at `0x18003a10d`
- `ntdll!NtGetNlsSectionPtr` at `0x18003a1aa`
- `ntdll!RtlUTF8ToUnicodeN` at `0x18003902a`
- `ntdll!RtlUTF8ToUnicodeN` at `0x18003902a`
- `ntdll!NtClose` at `0x180039de2`
- `ntdll!NtClose` at `0x180039de2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180039d84`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180039f73`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003a146`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003a24e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003a42f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003a592`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180039d84`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180039f73`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003a146`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003a24e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003a42f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003a592`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180039dae`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180039f9d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a124`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a16d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a1c1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a28f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a454`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a5b6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180039dae`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180039f9d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a124`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a16d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a1c1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a28f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a454`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a5b6`
- `ntdll!RtlAllocateHeap` at `0x18003a278`
- `ntdll!RtlAllocateHeap` at `0x18003a367`
- `ntdll!RtlAllocateHeap` at `0x18003a4a5`
- `ntdll!RtlAllocateHeap` at `0x18003a278`
- `ntdll!RtlAllocateHeap` at `0x18003a367`
- `ntdll!RtlAllocateHeap` at `0x18003a4a5`

## string_xrefs

- `0x180039c9d`: `\Registry\Machine\System\CurrentControlSet\Control`
- `0x18003a6e0`: `NlsDllCodePageTranslation`
- `0x18003a7f9`: `NlsDllCodePageTranslation`

## pseudocode

```c

```
