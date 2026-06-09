# __raise_securityfailure

- ea: `0x180002348`
- end: `0x18000237c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002390`
- `0x180002538`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x18000235c`
- `KERNEL32!UnhandledExceptionFilter` at `0x18000235c`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180002353`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180002353`
- `KERNEL32!GetCurrentProcess` at `0x180002362`
- `KERNEL32!GetCurrentProcess` at `0x180002362`
- `KERNEL32!TerminateProcess` at `0x180002375`

## pseudocode

```c
BOOL __fastcall _raise_securityfailure(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  HANDLE CurrentProcess; // rax

  SetUnhandledExceptionFilter(0);
  UnhandledExceptionFilter(ExceptionInfo);
  CurrentProcess = GetCurrentProcess();
  return TerminateProcess(CurrentProcess, 0xC0000409);
}

```

## disassembly

```asm
0x180002348  push    rbx
0x18000234a  sub     rsp, 20h
0x18000234e  mov     rbx, rcx
0x180002351  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180002353  call    cs:__imp_SetUnhandledExceptionFilter
0x180002359  mov     rcx, rbx; ExceptionInfo
0x18000235c  call    cs:__imp_UnhandledExceptionFilter
0x180002362  call    cs:__imp_GetCurrentProcess
0x180002368  mov     rcx, rax
0x18000236b  mov     edx, 0C0000409h
0x180002370  add     rsp, 20h
0x180002374  pop     rbx
0x180002375  jmp     cs:__imp_TerminateProcess
```
