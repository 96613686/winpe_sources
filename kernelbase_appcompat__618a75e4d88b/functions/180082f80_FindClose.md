# FindClose

- ea: `0x180082f80`
- end: `0x18008307b`
- name: `FindClose`
- size: `251`
- prototype: `BOOL __stdcall(HANDLE hFindFile)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007fdc0`
- `0x1800815d0`
- `0x180081780`
- `0x180082020`
- `0x180084c70`
- `0x1800cbaf0`
- `0x1800e26e0`
- `0x180118900`
- `0x18015de0c`
- `0x18015df80`

## callees

- `0x18004b9d0`
- `0x180082f80`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180083011`
- `ntdll!RtlDeleteCriticalSection` at `0x180083011`
- `ntdll!RtlEnterCriticalSection` at `0x180082fa5`
- `ntdll!RtlEnterCriticalSection` at `0x180082fa5`
- `ntdll!RtlLeaveCriticalSection` at `0x180082fcb`
- `ntdll!RtlLeaveCriticalSection` at `0x180082fcb`
- `ntdll!RtlSetLastWin32Error` at `0x18008306b`
- `ntdll!RtlSetLastWin32Error` at `0x18008306b`
- `ntdll!NtClose` at `0x180082fda`
- `ntdll!NtClose` at `0x180082fda`
- `ntdll!RtlFreeHeap` at `0x180083001`
- `ntdll!RtlFreeHeap` at `0x18008302f`
- `ntdll!RtlFreeHeap` at `0x180083001`
- `ntdll!RtlFreeHeap` at `0x18008302f`

## pseudocode

```c

```
