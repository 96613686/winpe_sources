# __raise_securityfailure

- ea: `0x140001554`
- end: `0x140001588`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001590`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x140001581`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000155f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000155f`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001568`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001568`
- `KERNEL32!GetCurrentProcess` at `0x14000156e`
- `KERNEL32!GetCurrentProcess` at `0x14000156e`

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
0x140001554  push    rbx
0x140001556  sub     rsp, 20h
0x14000155a  mov     rbx, rcx
0x14000155d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14000155f  call    cs:__imp_SetUnhandledExceptionFilter
0x140001565  mov     rcx, rbx; ExceptionInfo
0x140001568  call    cs:__imp_UnhandledExceptionFilter
0x14000156e  call    cs:__imp_GetCurrentProcess
0x140001574  mov     rcx, rax
0x140001577  mov     edx, 0C0000409h
0x14000157c  add     rsp, 20h
0x140001580  pop     rbx
0x140001581  jmp     cs:__imp_TerminateProcess
```
