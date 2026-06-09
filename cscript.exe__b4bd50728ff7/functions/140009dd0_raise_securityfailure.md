# __raise_securityfailure

- ea: `0x140009dd0`
- end: `0x140009e04`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140009e10`
- `0x140009fb8`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x140009de4`
- `KERNEL32!UnhandledExceptionFilter` at `0x140009de4`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140009ddb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140009ddb`
- `KERNEL32!GetCurrentProcess` at `0x140009dea`
- `KERNEL32!GetCurrentProcess` at `0x140009dea`
- `KERNEL32!TerminateProcess` at `0x140009dfd`

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
0x140009dd0  push    rbx
0x140009dd2  sub     rsp, 20h
0x140009dd6  mov     rbx, rcx
0x140009dd9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140009ddb  call    cs:__imp_SetUnhandledExceptionFilter
0x140009de1  mov     rcx, rbx; ExceptionInfo
0x140009de4  call    cs:__imp_UnhandledExceptionFilter
0x140009dea  call    cs:__imp_GetCurrentProcess
0x140009df0  mov     rcx, rax
0x140009df3  mov     edx, 0C0000409h
0x140009df8  add     rsp, 20h
0x140009dfc  pop     rbx
0x140009dfd  jmp     cs:__imp_TerminateProcess
```
