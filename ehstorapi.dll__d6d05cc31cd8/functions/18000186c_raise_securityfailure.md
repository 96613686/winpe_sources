# __raise_securityfailure

- ea: `0x18000186c`
- end: `0x1800018a0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800018b0`
- `0x180001a58`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001880`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001880`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001877`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001877`
- `KERNEL32!GetCurrentProcess` at `0x180001886`
- `KERNEL32!GetCurrentProcess` at `0x180001886`
- `KERNEL32!TerminateProcess` at `0x180001899`

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
0x18000186c  push    rbx
0x18000186e  sub     rsp, 20h
0x180001872  mov     rbx, rcx
0x180001875  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001877  call    cs:__imp_SetUnhandledExceptionFilter
0x18000187d  mov     rcx, rbx; ExceptionInfo
0x180001880  call    cs:__imp_UnhandledExceptionFilter
0x180001886  call    cs:__imp_GetCurrentProcess
0x18000188c  mov     rcx, rax
0x18000188f  mov     edx, 0C0000409h
0x180001894  add     rsp, 20h
0x180001898  pop     rbx
0x180001899  jmp     cs:__imp_TerminateProcess
```
