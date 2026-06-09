# __raise_securityfailure

- ea: `0x180001c6c`
- end: `0x180001ca0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001cb0`
- `0x180001e58`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001c80`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001c80`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001c77`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001c77`
- `KERNEL32!TerminateProcess` at `0x180001c99`
- `KERNEL32!GetCurrentProcess` at `0x180001c86`
- `KERNEL32!GetCurrentProcess` at `0x180001c86`

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
0x180001c6c  push    rbx
0x180001c6e  sub     rsp, 20h
0x180001c72  mov     rbx, rcx
0x180001c75  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001c77  call    cs:__imp_SetUnhandledExceptionFilter
0x180001c7d  mov     rcx, rbx; ExceptionInfo
0x180001c80  call    cs:__imp_UnhandledExceptionFilter
0x180001c86  call    cs:__imp_GetCurrentProcess
0x180001c8c  mov     rcx, rax
0x180001c8f  mov     edx, 0C0000409h
0x180001c94  add     rsp, 20h
0x180001c98  pop     rbx
0x180001c99  jmp     cs:__imp_TerminateProcess
```
