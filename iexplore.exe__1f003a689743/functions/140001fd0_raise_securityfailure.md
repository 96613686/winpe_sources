# __raise_securityfailure

- ea: `0x140001fd0`
- end: `0x140002004`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002010`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x140001fe4`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001fe4`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001fdb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001fdb`
- `KERNEL32!GetCurrentProcess` at `0x140001fea`
- `KERNEL32!GetCurrentProcess` at `0x140001fea`
- `KERNEL32!TerminateProcess` at `0x140001ffd`

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
0x140001fd0  push    rbx
0x140001fd2  sub     rsp, 20h
0x140001fd6  mov     rbx, rcx
0x140001fd9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001fdb  call    cs:__imp_SetUnhandledExceptionFilter
0x140001fe1  mov     rcx, rbx; ExceptionInfo
0x140001fe4  call    cs:__imp_UnhandledExceptionFilter
0x140001fea  call    cs:__imp_GetCurrentProcess
0x140001ff0  mov     rcx, rax
0x140001ff3  mov     edx, 0C0000409h
0x140001ff8  add     rsp, 20h
0x140001ffc  pop     rbx
0x140001ffd  jmp     cs:__imp_TerminateProcess
```
