# __raise_securityfailure

- ea: `0x180002210`
- end: `0x180002244`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002250`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x18000223d`
- `KERNEL32!GetCurrentProcess` at `0x18000222a`
- `KERNEL32!GetCurrentProcess` at `0x18000222a`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000221b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000221b`
- `KERNEL32!UnhandledExceptionFilter` at `0x180002224`
- `KERNEL32!UnhandledExceptionFilter` at `0x180002224`

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
0x180002210  push    rbx
0x180002212  sub     rsp, 20h
0x180002216  mov     rbx, rcx
0x180002219  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000221b  call    cs:__imp_SetUnhandledExceptionFilter
0x180002221  mov     rcx, rbx; ExceptionInfo
0x180002224  call    cs:__imp_UnhandledExceptionFilter
0x18000222a  call    cs:__imp_GetCurrentProcess
0x180002230  mov     rcx, rax
0x180002233  mov     edx, 0C0000409h
0x180002238  add     rsp, 20h
0x18000223c  pop     rbx
0x18000223d  jmp     cs:__imp_TerminateProcess
```
