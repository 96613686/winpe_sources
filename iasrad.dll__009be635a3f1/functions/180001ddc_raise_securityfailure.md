# __raise_securityfailure

- ea: `0x180001ddc`
- end: `0x180001e10`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001e20`
- `0x180001fc8`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001df0`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001df0`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001de7`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001de7`
- `KERNEL32!GetCurrentProcess` at `0x180001df6`
- `KERNEL32!GetCurrentProcess` at `0x180001df6`
- `KERNEL32!TerminateProcess` at `0x180001e09`

## pseudocode

```c

```
