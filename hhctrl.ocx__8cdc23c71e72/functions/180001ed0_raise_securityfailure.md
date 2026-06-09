# __raise_securityfailure

- ea: `0x180001ed0`
- end: `0x180001f04`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001f10`
- `0x1800020b8`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180001eea`
- `KERNEL32!GetCurrentProcess` at `0x180001eea`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001ee4`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001ee4`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001edb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001edb`
- `KERNEL32!TerminateProcess` at `0x180001efd`

## pseudocode

```c

```
