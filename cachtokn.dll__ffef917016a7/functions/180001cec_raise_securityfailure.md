# __raise_securityfailure

- ea: `0x180001cec`
- end: `0x180001d20`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001d30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001d00`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001d00`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001cf7`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001cf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001d06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001d06`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001d19`

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
0x180001cec  push    rbx
0x180001cee  sub     rsp, 20h
0x180001cf2  mov     rbx, rcx
0x180001cf5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001cf7  call    cs:__imp_SetUnhandledExceptionFilter
0x180001cfd  mov     rcx, rbx; ExceptionInfo
0x180001d00  call    cs:__imp_UnhandledExceptionFilter
0x180001d06  call    cs:__imp_GetCurrentProcess
0x180001d0c  mov     rcx, rax
0x180001d0f  mov     edx, 0C0000409h
0x180001d14  add     rsp, 20h
0x180001d18  pop     rbx
0x180001d19  jmp     cs:__imp_TerminateProcess
```
