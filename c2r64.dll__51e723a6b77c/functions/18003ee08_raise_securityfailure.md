# __raise_securityfailure

- ea: `0x18003ee08`
- end: `0x18003ee3c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18003ee40`
- `0x18003ef30`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18003ee22`
- `KERNEL32!GetCurrentProcess` at `0x18003ee22`
- `KERNEL32!TerminateProcess` at `0x18003ee35`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18003ee13`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18003ee13`
- `KERNEL32!UnhandledExceptionFilter` at `0x18003ee1c`
- `KERNEL32!UnhandledExceptionFilter` at `0x18003ee1c`

## pseudocode

```c

```
