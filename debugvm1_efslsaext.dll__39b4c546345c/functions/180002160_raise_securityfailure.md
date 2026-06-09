# __raise_securityfailure

- ea: `0x180002160`
- end: `0x180002194`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800021a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000216b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000216b`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002174`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002174`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000218d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000217a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000217a`

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
0x180002160  push    rbx
0x180002162  sub     rsp, 20h
0x180002166  mov     rbx, rcx
0x180002169  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000216b  call    cs:__imp_SetUnhandledExceptionFilter
0x180002171  mov     rcx, rbx; ExceptionInfo
0x180002174  call    cs:__imp_UnhandledExceptionFilter
0x18000217a  call    cs:__imp_GetCurrentProcess
0x180002180  mov     rcx, rax
0x180002183  mov     edx, 0C0000409h
0x180002188  add     rsp, 20h
0x18000218c  pop     rbx
0x18000218d  jmp     cs:__imp_TerminateProcess
```
