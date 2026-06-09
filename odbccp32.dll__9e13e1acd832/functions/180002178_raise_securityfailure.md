# __raise_securityfailure

- ea: `0x180002178`
- end: `0x1800021ac`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800021c0`
- `0x180002368`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x1800021a5`
- `KERNEL32!GetCurrentProcess` at `0x180002192`
- `KERNEL32!GetCurrentProcess` at `0x180002192`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180002183`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180002183`
- `KERNEL32!UnhandledExceptionFilter` at `0x18000218c`
- `KERNEL32!UnhandledExceptionFilter` at `0x18000218c`

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
0x180002178  push    rbx
0x18000217a  sub     rsp, 20h
0x18000217e  mov     rbx, rcx
0x180002181  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180002183  call    cs:__imp_SetUnhandledExceptionFilter
0x180002189  mov     rcx, rbx; ExceptionInfo
0x18000218c  call    cs:__imp_UnhandledExceptionFilter
0x180002192  call    cs:__imp_GetCurrentProcess
0x180002198  mov     rcx, rax
0x18000219b  mov     edx, 0C0000409h
0x1800021a0  add     rsp, 20h
0x1800021a4  pop     rbx
0x1800021a5  jmp     cs:__imp_TerminateProcess
```
