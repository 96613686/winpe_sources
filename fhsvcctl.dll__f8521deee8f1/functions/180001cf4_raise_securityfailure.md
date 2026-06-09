# __raise_securityfailure

- ea: `0x180001cf4`
- end: `0x180001d28`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001d30`

## import_xrefs

- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001cff`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001cff`
- `KERNEL32!TerminateProcess` at `0x180001d21`
- `KERNEL32!GetCurrentProcess` at `0x180001d0e`
- `KERNEL32!GetCurrentProcess` at `0x180001d0e`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001d08`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001d08`

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
0x180001cf4  push    rbx
0x180001cf6  sub     rsp, 20h
0x180001cfa  mov     rbx, rcx
0x180001cfd  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001cff  call    cs:__imp_SetUnhandledExceptionFilter
0x180001d05  mov     rcx, rbx; ExceptionInfo
0x180001d08  call    cs:__imp_UnhandledExceptionFilter
0x180001d0e  call    cs:__imp_GetCurrentProcess
0x180001d14  mov     rcx, rax
0x180001d17  mov     edx, 0C0000409h
0x180001d1c  add     rsp, 20h
0x180001d20  pop     rbx
0x180001d21  jmp     cs:__imp_TerminateProcess
```
