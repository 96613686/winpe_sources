# __raise_securityfailure

- ea: `0x180003088`
- end: `0x1800030bc`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800030d0`
- `0x180003278`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x18000309c`
- `KERNEL32!UnhandledExceptionFilter` at `0x18000309c`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180003093`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180003093`
- `KERNEL32!GetCurrentProcess` at `0x1800030a2`
- `KERNEL32!GetCurrentProcess` at `0x1800030a2`
- `KERNEL32!TerminateProcess` at `0x1800030b5`

## pseudocode

```c

```
