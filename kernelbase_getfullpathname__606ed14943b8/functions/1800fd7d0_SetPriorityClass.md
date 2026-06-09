# SetPriorityClass

- ea: `0x1800fd7d0`
- end: `0x1800fd9e5`
- name: `SetPriorityClass`
- size: `533`
- prototype: `BOOL __stdcall(HANDLE hProcess, DWORD dwPriorityClass)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004b9d0`
- `0x1800fd7d0`
- `0x1800fd9ec`
- `0x1800fdaf4`
- `0x18012e338`
- `0x1801369c9`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800fd93d`
- `ntdll!RtlSetLastWin32Error` at `0x1800fd98f`
- `ntdll!RtlSetLastWin32Error` at `0x1800fd93d`
- `ntdll!RtlSetLastWin32Error` at `0x1800fd98f`
- `ntdll!RtlReleasePrivilege` at `0x1800fd9a0`
- `ntdll!RtlReleasePrivilege` at `0x1800fd9a0`
- `ntdll!NtSetInformationProcess` at `0x1800fd8b6`
- `ntdll!NtSetInformationProcess` at `0x1800fd8b6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800fd814`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800fd814`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800fd865`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800fd865`
- `ntdll!NtCompareObjects` at `0x1800fd951`
- `ntdll!NtCompareObjects` at `0x1800fd951`

## pseudocode

```c

```
