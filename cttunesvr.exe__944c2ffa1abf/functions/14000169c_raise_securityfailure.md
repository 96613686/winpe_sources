# __raise_securityfailure

- ea: `0x14000169c`
- end: `0x1400016d0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400016e0`
- `0x140001888`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x1400016c9`
- `KERNEL32!GetCurrentProcess` at `0x1400016b6`
- `KERNEL32!GetCurrentProcess` at `0x1400016b6`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400016a7`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400016a7`
- `KERNEL32!UnhandledExceptionFilter` at `0x1400016b0`
- `KERNEL32!UnhandledExceptionFilter` at `0x1400016b0`

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
0x14000169c  push    rbx
0x14000169e  sub     rsp, 20h
0x1400016a2  mov     rbx, rcx
0x1400016a5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1400016a7  call    cs:__imp_SetUnhandledExceptionFilter
0x1400016ad  mov     rcx, rbx; ExceptionInfo
0x1400016b0  call    cs:__imp_UnhandledExceptionFilter
0x1400016b6  call    cs:__imp_GetCurrentProcess
0x1400016bc  mov     rcx, rax
0x1400016bf  mov     edx, 0C0000409h
0x1400016c4  add     rsp, 20h
0x1400016c8  pop     rbx
0x1400016c9  jmp     cs:__imp_TerminateProcess
```
