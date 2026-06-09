# __raise_securityfailure

- ea: `0x140002438`
- end: `0x14000246c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002480`
- `0x140002628`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x140002465`
- `KERNEL32!UnhandledExceptionFilter` at `0x14000244c`
- `KERNEL32!UnhandledExceptionFilter` at `0x14000244c`
- `KERNEL32!GetCurrentProcess` at `0x140002452`
- `KERNEL32!GetCurrentProcess` at `0x140002452`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140002443`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140002443`

## pseudocode

```c

```
