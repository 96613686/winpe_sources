# __raise_securityfailure

- ea: `0x140001adc`
- end: `0x140001b10`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001b20`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x140001af6`
- `KERNEL32!GetCurrentProcess` at `0x140001af6`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001af0`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001af0`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001ae7`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001ae7`
- `KERNEL32!TerminateProcess` at `0x140001b09`

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
0x140001adc  push    rbx
0x140001ade  sub     rsp, 20h
0x140001ae2  mov     rbx, rcx
0x140001ae5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001ae7  call    cs:__imp_SetUnhandledExceptionFilter
0x140001aed  mov     rcx, rbx; ExceptionInfo
0x140001af0  call    cs:__imp_UnhandledExceptionFilter
0x140001af6  call    cs:__imp_GetCurrentProcess
0x140001afc  mov     rcx, rax
0x140001aff  mov     edx, 0C0000409h
0x140001b04  add     rsp, 20h
0x140001b08  pop     rbx
0x140001b09  jmp     cs:__imp_TerminateProcess
```
