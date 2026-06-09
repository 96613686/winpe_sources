# __raise_securityfailure

- ea: `0x180001d9c`
- end: `0x180001dd0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001de0`
- `0x180001f88`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001db0`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001db0`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001da7`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001da7`
- `KERNEL32!GetCurrentProcess` at `0x180001db6`
- `KERNEL32!GetCurrentProcess` at `0x180001db6`
- `KERNEL32!TerminateProcess` at `0x180001dc9`

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
0x180001d9c  push    rbx
0x180001d9e  sub     rsp, 20h
0x180001da2  mov     rbx, rcx
0x180001da5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001da7  call    cs:__imp_SetUnhandledExceptionFilter
0x180001dad  mov     rcx, rbx; ExceptionInfo
0x180001db0  call    cs:__imp_UnhandledExceptionFilter
0x180001db6  call    cs:__imp_GetCurrentProcess
0x180001dbc  mov     rcx, rax
0x180001dbf  mov     edx, 0C0000409h
0x180001dc4  add     rsp, 20h
0x180001dc8  pop     rbx
0x180001dc9  jmp     cs:__imp_TerminateProcess
```
