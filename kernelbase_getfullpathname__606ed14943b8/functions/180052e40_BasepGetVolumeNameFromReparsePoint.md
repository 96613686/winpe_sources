# BasepGetVolumeNameFromReparsePoint

- ea: `0x180052e40`
- end: `0x180053323`
- name: `BasepGetVolumeNameFromReparsePoint`
- size: `1251`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, void *, DWORD cchFilePath)`
- caller_count: `3`
- callee_count: `11`
- tags: `reparse_path, loader_planting`

## callers

- `0x180050cc0`
- `0x180050eb0`
- `0x180052890`

## callees

- `0x18004b9d0`
- `0x18004c490`
- `0x180052e40`
- `0x180053330`
- `0x1800533cc`
- `0x180053c30`
- `0x180083ac0`
- `0x18013877c`
- `0x180194eb9`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!SbSelectProcedure` at `0x180053039`
- `ntdll!SbSelectProcedure` at `0x180053039`
- `ntdll!RtlSetLastWin32Error` at `0x180052f42`
- `ntdll!RtlSetLastWin32Error` at `0x180053139`
- `ntdll!RtlSetLastWin32Error` at `0x180053169`
- `ntdll!RtlSetLastWin32Error` at `0x180053274`
- `ntdll!RtlSetLastWin32Error` at `0x18019ab1f`
- `ntdll!RtlSetLastWin32Error` at `0x180052f42`
- `ntdll!RtlSetLastWin32Error` at `0x180053139`
- `ntdll!RtlSetLastWin32Error` at `0x180053169`
- `ntdll!RtlSetLastWin32Error` at `0x180053274`
- `ntdll!RtlSetLastWin32Error` at `0x18019ab1f`
- `ntdll!NtClose` at `0x18005304d`
- `ntdll!NtClose` at `0x18005304d`
- `ntdll!RtlFreeHeap` at `0x180052ff5`
- `ntdll!RtlFreeHeap` at `0x180052ff5`
- `ntdll!RtlAllocateHeap` at `0x180052f67`
- `ntdll!RtlAllocateHeap` at `0x180052f67`

## pseudocode

```c

```
