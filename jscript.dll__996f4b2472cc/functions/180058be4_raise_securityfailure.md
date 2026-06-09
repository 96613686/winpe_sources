# __raise_securityfailure

- ea: `0x180058be4`
- end: `0x180058c18`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180058c20`
- `0x180058dc8`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180058bf8`
- `KERNEL32!UnhandledExceptionFilter` at `0x180058bf8`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180058bef`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180058bef`
- `KERNEL32!GetCurrentProcess` at `0x180058bfe`
- `KERNEL32!GetCurrentProcess` at `0x180058bfe`
- `KERNEL32!TerminateProcess` at `0x180058c11`

## pseudocode

```c

```
