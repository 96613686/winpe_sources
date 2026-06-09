# __raise_securityfailure

- ea: `0x18003e00c`
- end: `0x18003e040`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18003e040`
- `0x18003e128`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x18003e039`
- `KERNEL32!GetCurrentProcess` at `0x18003e026`
- `KERNEL32!GetCurrentProcess` at `0x18003e026`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18003e017`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18003e017`
- `KERNEL32!UnhandledExceptionFilter` at `0x18003e020`
- `KERNEL32!UnhandledExceptionFilter` at `0x18003e020`

## pseudocode

```c

```
