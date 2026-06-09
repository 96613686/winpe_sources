# __raise_securityfailure

- ea: `0x180063ce8`
- end: `0x180063d1c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180063d30`
- `0x180063ed8`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180063d15`
- `KERNEL32!GetCurrentProcess` at `0x180063d02`
- `KERNEL32!GetCurrentProcess` at `0x180063d02`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180063cf3`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180063cf3`
- `KERNEL32!UnhandledExceptionFilter` at `0x180063cfc`
- `KERNEL32!UnhandledExceptionFilter` at `0x180063cfc`

## pseudocode

```c

```
