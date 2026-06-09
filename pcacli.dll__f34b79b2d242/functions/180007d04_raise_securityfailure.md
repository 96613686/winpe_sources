# __raise_securityfailure

- ea: `0x180007d04`
- end: `0x180007d38`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007d40`
- `0x180007ee8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007d1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007d1e`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180007d31`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180007d18`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180007d18`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180007d0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180007d0f`

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
0x180007d04  push    rbx
0x180007d06  sub     rsp, 20h
0x180007d0a  mov     rbx, rcx
0x180007d0d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180007d0f  call    cs:__imp_SetUnhandledExceptionFilter
0x180007d15  mov     rcx, rbx; ExceptionInfo
0x180007d18  call    cs:__imp_UnhandledExceptionFilter
0x180007d1e  call    cs:__imp_GetCurrentProcess
0x180007d24  mov     rcx, rax
0x180007d27  mov     edx, 0C0000409h
0x180007d2c  add     rsp, 20h
0x180007d30  pop     rbx
0x180007d31  jmp     cs:__imp_TerminateProcess
```
