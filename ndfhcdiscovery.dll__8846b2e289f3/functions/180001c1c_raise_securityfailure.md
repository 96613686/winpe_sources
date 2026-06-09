# __raise_securityfailure

- ea: `0x180001c1c`
- end: `0x180001c50`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001c60`
- `0x180001e08`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001c49`
- `KERNEL32!GetCurrentProcess` at `0x180001c36`
- `KERNEL32!GetCurrentProcess` at `0x180001c36`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001c27`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001c27`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001c30`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001c30`

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
0x180001c1c  push    rbx
0x180001c1e  sub     rsp, 20h
0x180001c22  mov     rbx, rcx
0x180001c25  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001c27  call    cs:__imp_SetUnhandledExceptionFilter
0x180001c2d  mov     rcx, rbx; ExceptionInfo
0x180001c30  call    cs:__imp_UnhandledExceptionFilter
0x180001c36  call    cs:__imp_GetCurrentProcess
0x180001c3c  mov     rcx, rax
0x180001c3f  mov     edx, 0C0000409h
0x180001c44  add     rsp, 20h
0x180001c48  pop     rbx
0x180001c49  jmp     cs:__imp_TerminateProcess
```
