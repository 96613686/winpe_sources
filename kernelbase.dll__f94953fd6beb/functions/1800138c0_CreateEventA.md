# CreateEventA

- ea: `0x1800138c0`
- end: `0x180013aef`
- name: `CreateEventA`
- size: `559`
- prototype: `HANDLE __stdcall(LPSECURITY_ATTRIBUTES lpEventAttributes, BOOL bManualReset, BOOL bInitialState, LPCSTR lpName)`
- caller_count: `26`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800f0120`
- `0x1800f5fc8`
- `0x1800f89bc`
- `0x1800fd010`
- `0x180102430`
- `0x18010508c`
- `0x1801057f4`
- `0x180107750`
- `0x18010a210`
- `0x18010a870`
- `0x18010a9c0`
- `0x18010af50`
- `0x18010afb0`
- `0x18010b1f8`
- `0x18010e01c`
- `0x18010fce8`
- `0x1801103d4`
- `0x180110590`
- `0x180110f5c`
- `0x180128ea0`
- `0x18013299c`
- `0x18017df40`
- `0x18017e190`
- `0x18017e510`
- `0x18017e790`
- `0x18017e880`

## callees

- `0x1800134a0`
- `0x1800138c0`
- `0x18006e3f0`
- `0x180197010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180013a50`
- `ntdll!RtlFreeUnicodeString` at `0x180013a50`
- `ntdll!RtlInitUnicodeString` at `0x1800139bd`
- `ntdll!RtlInitUnicodeString` at `0x1800139bd`
- `ntdll!RtlSetLastWin32Error` at `0x18001395c`
- `ntdll!RtlSetLastWin32Error` at `0x180013ac5`
- `ntdll!RtlSetLastWin32Error` at `0x180013ad9`
- `ntdll!RtlSetLastWin32Error` at `0x18001395c`
- `ntdll!RtlSetLastWin32Error` at `0x180013ac5`
- `ntdll!RtlSetLastWin32Error` at `0x180013ad9`
- `ntdll!NtCreateEvent` at `0x180013941`
- `ntdll!NtCreateEvent` at `0x180013941`
- `ntdll!RtlInitAnsiStringEx` at `0x180013a7b`
- `ntdll!RtlInitAnsiStringEx` at `0x180013a7b`

## pseudocode

```c

```
