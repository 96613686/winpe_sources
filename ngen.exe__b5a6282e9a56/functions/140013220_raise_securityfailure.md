# __raise_securityfailure

- ea: `0x140013220`
- end: `0x140013254`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140013260`
- `0x140013348`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x14001324d`
- `KERNEL32!GetCurrentProcess` at `0x14001323a`
- `KERNEL32!GetCurrentProcess` at `0x14001323a`
- `KERNEL32!UnhandledExceptionFilter` at `0x140013234`
- `KERNEL32!UnhandledExceptionFilter` at `0x140013234`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14001322b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14001322b`

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
0x140013220  push    rbx
0x140013222  sub     rsp, 20h
0x140013226  mov     rbx, rcx
0x140013229  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14001322b  call    cs:__imp_SetUnhandledExceptionFilter
0x140013231  mov     rcx, rbx; ExceptionInfo
0x140013234  call    cs:__imp_UnhandledExceptionFilter
0x14001323a  call    cs:__imp_GetCurrentProcess
0x140013240  mov     rcx, rax
0x140013243  mov     edx, 0C0000409h
0x140013248  add     rsp, 20h
0x14001324c  pop     rbx
0x14001324d  jmp     cs:__imp_TerminateProcess
```
