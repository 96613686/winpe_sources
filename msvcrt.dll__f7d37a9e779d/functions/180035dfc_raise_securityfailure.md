# __raise_securityfailure

- ea: `0x180035dfc`
- end: `0x180035e30`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180035e40`
- `0x180035fe8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180035e07`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180035e07`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180035e10`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180035e10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180035e16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180035e16`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180035e29`

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
0x180035dfc  push    rbx
0x180035dfe  sub     rsp, 20h
0x180035e02  mov     rbx, rcx
0x180035e05  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180035e07  call    cs:__imp_SetUnhandledExceptionFilter
0x180035e0d  mov     rcx, rbx; ExceptionInfo
0x180035e10  call    cs:__imp_UnhandledExceptionFilter
0x180035e16  call    cs:__imp_GetCurrentProcess
0x180035e1c  mov     rcx, rax
0x180035e1f  mov     edx, 0C0000409h
0x180035e24  add     rsp, 20h
0x180035e28  pop     rbx
0x180035e29  jmp     cs:__imp_TerminateProcess
```
