# __raise_securityfailure

- ea: `0x1800014f0`
- end: `0x180001524`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001530`
- `0x1800016d8`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001504`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001504`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800014fb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800014fb`
- `KERNEL32!TerminateProcess` at `0x18000151d`
- `KERNEL32!GetCurrentProcess` at `0x18000150a`
- `KERNEL32!GetCurrentProcess` at `0x18000150a`

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
0x1800014f0  push    rbx
0x1800014f2  sub     rsp, 20h
0x1800014f6  mov     rbx, rcx
0x1800014f9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800014fb  call    cs:__imp_SetUnhandledExceptionFilter
0x180001501  mov     rcx, rbx; ExceptionInfo
0x180001504  call    cs:__imp_UnhandledExceptionFilter
0x18000150a  call    cs:__imp_GetCurrentProcess
0x180001510  mov     rcx, rax
0x180001513  mov     edx, 0C0000409h
0x180001518  add     rsp, 20h
0x18000151c  pop     rbx
0x18000151d  jmp     cs:__imp_TerminateProcess
```
