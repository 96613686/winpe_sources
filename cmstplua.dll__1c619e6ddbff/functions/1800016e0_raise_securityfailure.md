# __raise_securityfailure

- ea: `0x1800016e0`
- end: `0x180001714`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001720`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x18000170d`
- `KERNEL32!GetCurrentProcess` at `0x1800016fa`
- `KERNEL32!GetCurrentProcess` at `0x1800016fa`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800016eb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800016eb`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800016f4`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800016f4`

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
0x1800016e0  push    rbx
0x1800016e2  sub     rsp, 20h
0x1800016e6  mov     rbx, rcx
0x1800016e9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800016eb  call    cs:__imp_SetUnhandledExceptionFilter
0x1800016f1  mov     rcx, rbx; ExceptionInfo
0x1800016f4  call    cs:__imp_UnhandledExceptionFilter
0x1800016fa  call    cs:__imp_GetCurrentProcess
0x180001700  mov     rcx, rax
0x180001703  mov     edx, 0C0000409h
0x180001708  add     rsp, 20h
0x18000170c  pop     rbx
0x18000170d  jmp     cs:__imp_TerminateProcess
```
