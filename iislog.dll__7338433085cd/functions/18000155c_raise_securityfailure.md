# __raise_securityfailure

- ea: `0x18000155c`
- end: `0x180001590`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800015a0`
- `0x180001748`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180001576`
- `KERNEL32!GetCurrentProcess` at `0x180001576`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001570`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001570`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001567`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001567`
- `KERNEL32!TerminateProcess` at `0x180001589`

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
0x18000155c  push    rbx
0x18000155e  sub     rsp, 20h
0x180001562  mov     rbx, rcx
0x180001565  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001567  call    cs:__imp_SetUnhandledExceptionFilter
0x18000156d  mov     rcx, rbx; ExceptionInfo
0x180001570  call    cs:__imp_UnhandledExceptionFilter
0x180001576  call    cs:__imp_GetCurrentProcess
0x18000157c  mov     rcx, rax
0x18000157f  mov     edx, 0C0000409h
0x180001584  add     rsp, 20h
0x180001588  pop     rbx
0x180001589  jmp     cs:__imp_TerminateProcess
```
