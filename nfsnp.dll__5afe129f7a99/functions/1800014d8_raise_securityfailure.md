# __raise_securityfailure

- ea: `0x1800014d8`
- end: `0x18000150c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001520`
- `0x1800016c8`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1800014f2`
- `KERNEL32!GetCurrentProcess` at `0x1800014f2`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800014ec`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800014ec`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800014e3`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800014e3`
- `KERNEL32!TerminateProcess` at `0x180001505`

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
0x1800014d8  push    rbx
0x1800014da  sub     rsp, 20h
0x1800014de  mov     rbx, rcx
0x1800014e1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800014e3  call    cs:__imp_SetUnhandledExceptionFilter
0x1800014e9  mov     rcx, rbx; ExceptionInfo
0x1800014ec  call    cs:__imp_UnhandledExceptionFilter
0x1800014f2  call    cs:__imp_GetCurrentProcess
0x1800014f8  mov     rcx, rax
0x1800014fb  mov     edx, 0C0000409h
0x180001500  add     rsp, 20h
0x180001504  pop     rbx
0x180001505  jmp     cs:__imp_TerminateProcess
```
