# __raise_securityfailure

- ea: `0x1400016ec`
- end: `0x140001720`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001730`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x140001706`
- `KERNEL32!GetCurrentProcess` at `0x140001706`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001700`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001700`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400016f7`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400016f7`
- `KERNEL32!TerminateProcess` at `0x140001719`

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
0x1400016ec  push    rbx
0x1400016ee  sub     rsp, 20h
0x1400016f2  mov     rbx, rcx
0x1400016f5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1400016f7  call    cs:__imp_SetUnhandledExceptionFilter
0x1400016fd  mov     rcx, rbx; ExceptionInfo
0x140001700  call    cs:__imp_UnhandledExceptionFilter
0x140001706  call    cs:__imp_GetCurrentProcess
0x14000170c  mov     rcx, rax
0x14000170f  mov     edx, 0C0000409h
0x140001714  add     rsp, 20h
0x140001718  pop     rbx
0x140001719  jmp     cs:__imp_TerminateProcess
```
