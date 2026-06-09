# __raise_securityfailure

- ea: `0x18000d454`
- end: `0x18000d488`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000d490`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x18000d468`
- `KERNEL32!UnhandledExceptionFilter` at `0x18000d468`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000d45f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000d45f`
- `KERNEL32!TerminateProcess` at `0x18000d481`
- `KERNEL32!GetCurrentProcess` at `0x18000d46e`
- `KERNEL32!GetCurrentProcess` at `0x18000d46e`

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
0x18000d454  push    rbx
0x18000d456  sub     rsp, 20h
0x18000d45a  mov     rbx, rcx
0x18000d45d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000d45f  call    cs:__imp_SetUnhandledExceptionFilter
0x18000d465  mov     rcx, rbx; ExceptionInfo
0x18000d468  call    cs:__imp_UnhandledExceptionFilter
0x18000d46e  call    cs:__imp_GetCurrentProcess
0x18000d474  mov     rcx, rax
0x18000d477  mov     edx, 0C0000409h
0x18000d47c  add     rsp, 20h
0x18000d480  pop     rbx
0x18000d481  jmp     cs:__imp_TerminateProcess
```
