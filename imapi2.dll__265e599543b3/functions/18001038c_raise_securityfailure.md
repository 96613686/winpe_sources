# __raise_securityfailure

- ea: `0x18001038c`
- end: `0x1800103c0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800103d0`
- `0x180010578`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x1800103b9`
- `KERNEL32!GetCurrentProcess` at `0x1800103a6`
- `KERNEL32!GetCurrentProcess` at `0x1800103a6`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180010397`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180010397`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800103a0`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800103a0`

## pseudocode

```c

```
