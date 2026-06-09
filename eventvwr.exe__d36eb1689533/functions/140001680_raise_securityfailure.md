# __raise_securityfailure

- ea: `0x140001680`
- end: `0x1400016b4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400016c0`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x140001694`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001694`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000168b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000168b`
- `KERNEL32!TerminateProcess` at `0x1400016ad`
- `KERNEL32!GetCurrentProcess` at `0x14000169a`
- `KERNEL32!GetCurrentProcess` at `0x14000169a`

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
0x140001680  push    rbx
0x140001682  sub     rsp, 20h
0x140001686  mov     rbx, rcx
0x140001689  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14000168b  call    cs:__imp_SetUnhandledExceptionFilter
0x140001691  mov     rcx, rbx; ExceptionInfo
0x140001694  call    cs:__imp_UnhandledExceptionFilter
0x14000169a  call    cs:__imp_GetCurrentProcess
0x1400016a0  mov     rcx, rax
0x1400016a3  mov     edx, 0C0000409h
0x1400016a8  add     rsp, 20h
0x1400016ac  pop     rbx
0x1400016ad  jmp     cs:__imp_TerminateProcess
```
