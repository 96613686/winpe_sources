# __raise_securityfailure

- ea: `0x180001b04`
- end: `0x180001b38`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001b40`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001b18`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001b18`
- `KERNEL32!GetCurrentProcess` at `0x180001b1e`
- `KERNEL32!GetCurrentProcess` at `0x180001b1e`
- `KERNEL32!TerminateProcess` at `0x180001b31`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001b0f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001b0f`

## pseudocode

```c

```
