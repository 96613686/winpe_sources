# __raise_securityfailure

- ea: `0x180002058`
- end: `0x18000208c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800020a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002063`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002063`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000206c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000206c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002072`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002072`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002085`

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
0x180002058  push    rbx
0x18000205a  sub     rsp, 20h
0x18000205e  mov     rbx, rcx
0x180002061  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180002063  call    cs:__imp_SetUnhandledExceptionFilter
0x180002069  mov     rcx, rbx; ExceptionInfo
0x18000206c  call    cs:__imp_UnhandledExceptionFilter
0x180002072  call    cs:__imp_GetCurrentProcess
0x180002078  mov     rcx, rax
0x18000207b  mov     edx, 0C0000409h
0x180002080  add     rsp, 20h
0x180002084  pop     rbx
0x180002085  jmp     cs:__imp_TerminateProcess
```
