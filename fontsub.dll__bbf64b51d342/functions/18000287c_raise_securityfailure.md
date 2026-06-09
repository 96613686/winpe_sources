# __raise_securityfailure

- ea: `0x18000287c`
- end: `0x1800028b0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800028c0`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x1800028a9`
- `KERNEL32!GetCurrentProcess` at `0x180002896`
- `KERNEL32!GetCurrentProcess` at `0x180002896`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180002887`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180002887`
- `KERNEL32!UnhandledExceptionFilter` at `0x180002890`
- `KERNEL32!UnhandledExceptionFilter` at `0x180002890`

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
0x18000287c  push    rbx
0x18000287e  sub     rsp, 20h
0x180002882  mov     rbx, rcx
0x180002885  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180002887  call    cs:__imp_SetUnhandledExceptionFilter
0x18000288d  mov     rcx, rbx; ExceptionInfo
0x180002890  call    cs:__imp_UnhandledExceptionFilter
0x180002896  call    cs:__imp_GetCurrentProcess
0x18000289c  mov     rcx, rax
0x18000289f  mov     edx, 0C0000409h
0x1800028a4  add     rsp, 20h
0x1800028a8  pop     rbx
0x1800028a9  jmp     cs:__imp_TerminateProcess
```
