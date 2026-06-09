# __raise_securityfailure

- ea: `0x180015344`
- end: `0x180015378`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180015380`
- `0x180015528`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001535e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001535e`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180015371`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18001534f`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18001534f`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180015358`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180015358`

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
0x180015344  push    rbx
0x180015346  sub     rsp, 20h
0x18001534a  mov     rbx, rcx
0x18001534d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18001534f  call    cs:__imp_SetUnhandledExceptionFilter
0x180015355  mov     rcx, rbx; ExceptionInfo
0x180015358  call    cs:__imp_UnhandledExceptionFilter
0x18001535e  call    cs:__imp_GetCurrentProcess
0x180015364  mov     rcx, rax
0x180015367  mov     edx, 0C0000409h
0x18001536c  add     rsp, 20h
0x180015370  pop     rbx
0x180015371  jmp     cs:__imp_TerminateProcess
```
