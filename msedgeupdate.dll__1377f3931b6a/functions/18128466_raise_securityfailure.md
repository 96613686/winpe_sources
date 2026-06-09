# ___raise_securityfailure

- ea: `0x18128466`
- end: `0x1812848e`
- name: `___raise_securityfailure`
- size: `40`
- prototype: `BOOL __cdecl(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1812848e`
- `0x18128594`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1812847f`
- `KERNEL32!GetCurrentProcess` at `0x1812847f`
- `KERNEL32!TerminateProcess` at `0x18128486`
- `KERNEL32!TerminateProcess` at `0x18128486`
- `KERNEL32!UnhandledExceptionFilter` at `0x18128474`
- `KERNEL32!UnhandledExceptionFilter` at `0x18128474`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1812846b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1812846b`

## pseudocode

```c

```
