# __raise_securityfailure

- ea: `0x1800f0ebc`
- end: `0x1800f0ef0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800f0ef0`
- `0x1800f0fd8`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1800f0ed6`
- `KERNEL32!GetCurrentProcess` at `0x1800f0ed6`
- `KERNEL32!TerminateProcess` at `0x1800f0ee9`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800f0ed0`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800f0ed0`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800f0ec7`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800f0ec7`

## pseudocode

```c

```
