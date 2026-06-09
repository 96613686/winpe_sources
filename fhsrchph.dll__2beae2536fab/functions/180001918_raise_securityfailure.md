# __raise_securityfailure

- ea: `0x180001918`
- end: `0x18000194c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001960`
- `0x180001b08`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x18000192c`
- `KERNEL32!UnhandledExceptionFilter` at `0x18000192c`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001923`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001923`
- `KERNEL32!GetCurrentProcess` at `0x180001932`
- `KERNEL32!GetCurrentProcess` at `0x180001932`
- `KERNEL32!TerminateProcess` at `0x180001945`

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
0x180001918  push    rbx
0x18000191a  sub     rsp, 20h
0x18000191e  mov     rbx, rcx
0x180001921  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001923  call    cs:__imp_SetUnhandledExceptionFilter
0x180001929  mov     rcx, rbx; ExceptionInfo
0x18000192c  call    cs:__imp_UnhandledExceptionFilter
0x180001932  call    cs:__imp_GetCurrentProcess
0x180001938  mov     rcx, rax
0x18000193b  mov     edx, 0C0000409h
0x180001940  add     rsp, 20h
0x180001944  pop     rbx
0x180001945  jmp     cs:__imp_TerminateProcess
```
