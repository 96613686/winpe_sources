# __raise_securityfailure

- ea: `0x180001af0`
- end: `0x180001b24`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001b30`
- `0x180001cd8`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001b1d`
- `KERNEL32!GetCurrentProcess` at `0x180001b0a`
- `KERNEL32!GetCurrentProcess` at `0x180001b0a`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001afb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001afb`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001b04`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001b04`

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
0x180001af0  push    rbx
0x180001af2  sub     rsp, 20h
0x180001af6  mov     rbx, rcx
0x180001af9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001afb  call    cs:__imp_SetUnhandledExceptionFilter
0x180001b01  mov     rcx, rbx; ExceptionInfo
0x180001b04  call    cs:__imp_UnhandledExceptionFilter
0x180001b0a  call    cs:__imp_GetCurrentProcess
0x180001b10  mov     rcx, rax
0x180001b13  mov     edx, 0C0000409h
0x180001b18  add     rsp, 20h
0x180001b1c  pop     rbx
0x180001b1d  jmp     cs:__imp_TerminateProcess
```
