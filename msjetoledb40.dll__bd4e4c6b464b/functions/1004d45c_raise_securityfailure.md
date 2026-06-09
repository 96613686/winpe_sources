# ___raise_securityfailure

- ea: `0x1004d45c`
- end: `0x1004d486`
- name: `___raise_securityfailure`
- size: `42`
- prototype: `int __cdecl(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1004d48c`
- `0x1004d5a1`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x1004d47e`
- `KERNEL32!TerminateProcess` at `0x1004d47e`
- `KERNEL32!GetCurrentProcess` at `0x1004d477`
- `KERNEL32!GetCurrentProcess` at `0x1004d477`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1004d463`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1004d463`
- `KERNEL32!UnhandledExceptionFilter` at `0x1004d46c`
- `KERNEL32!UnhandledExceptionFilter` at `0x1004d46c`

## pseudocode

```c
BOOL __cdecl __raise_securityfailure(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  HANDLE CurrentProcess; // eax

  SetUnhandledExceptionFilter(0);
  UnhandledExceptionFilter(ExceptionInfo);
  CurrentProcess = GetCurrentProcess();
  return TerminateProcess(CurrentProcess, 0xC0000409);
}

```

## disassembly

```asm
0x1004d45c  mov     edi, edi
0x1004d45e  push    ebp
0x1004d45f  mov     ebp, esp
0x1004d461  push    0; lpTopLevelExceptionFilter
0x1004d463  call    ds:__imp__SetUnhandledExceptionFilter@4; SetUnhandledExceptionFilter(x)
0x1004d469  push    [ebp+ExceptionInfo]; ExceptionInfo
0x1004d46c  call    ds:__imp__UnhandledExceptionFilter@4; UnhandledExceptionFilter(x)
0x1004d472  push    0C0000409h; uExitCode
0x1004d477  call    ds:__imp__GetCurrentProcess@0; GetCurrentProcess()
0x1004d47d  push    eax; hProcess
0x1004d47e  call    ds:__imp__TerminateProcess@8; TerminateProcess(x,x)
0x1004d484  pop     ebp
0x1004d485  retn
```
