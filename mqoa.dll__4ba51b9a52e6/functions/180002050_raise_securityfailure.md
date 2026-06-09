# __raise_securityfailure

- ea: `0x180002050`
- end: `0x180002084`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002090`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180002064`
- `KERNEL32!UnhandledExceptionFilter` at `0x180002064`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000205b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000205b`
- `KERNEL32!TerminateProcess` at `0x18000207d`
- `KERNEL32!GetCurrentProcess` at `0x18000206a`
- `KERNEL32!GetCurrentProcess` at `0x18000206a`

## pseudocode

```c

```
