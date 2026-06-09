# DoConnectThreadFunc(void *)

- ea: `0x1801940e0`
- end: `0x1801941da`
- name: `?DoConnectThreadFunc@@YAKPEAX@Z`
- size: `250`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180003030`
- `0x180003824`
- `0x18001cb10`
- `0x1801940e0`
- `0x180195030`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180194180`
- `KERNEL32!SetEvent` at `0x180194180`
- `KERNEL32!CloseHandle` at `0x180194198`
- `KERNEL32!CloseHandle` at `0x180194198`
- `ADVAPI32!RevertToSelf` at `0x18019415f`
- `ADVAPI32!RevertToSelf` at `0x18019415f`

## pseudocode

```c

```
