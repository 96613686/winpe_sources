# __raise_securityfailure

- ea: `0x18000175c`
- end: `0x180001790`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800017a0`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001789`
- `KERNEL32!GetCurrentProcess` at `0x180001776`
- `KERNEL32!GetCurrentProcess` at `0x180001776`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001767`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001767`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001770`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001770`

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
0x18000175c  push    rbx
0x18000175e  sub     rsp, 20h
0x180001762  mov     rbx, rcx
0x180001765  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001767  call    cs:__imp_SetUnhandledExceptionFilter
0x18000176d  mov     rcx, rbx; ExceptionInfo
0x180001770  call    cs:__imp_UnhandledExceptionFilter
0x180001776  call    cs:__imp_GetCurrentProcess
0x18000177c  mov     rcx, rax
0x18000177f  mov     edx, 0C0000409h
0x180001784  add     rsp, 20h
0x180001788  pop     rbx
0x180001789  jmp     cs:__imp_TerminateProcess
```
