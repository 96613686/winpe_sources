# __raise_securityfailure

- ea: `0x18000494c`
- end: `0x180004980`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180004990`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004966`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004966`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180004979`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180004957`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180004957`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180004960`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180004960`

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
0x18000494c  push    rbx
0x18000494e  sub     rsp, 20h
0x180004952  mov     rbx, rcx
0x180004955  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180004957  call    cs:__imp_SetUnhandledExceptionFilter
0x18000495d  mov     rcx, rbx; ExceptionInfo
0x180004960  call    cs:__imp_UnhandledExceptionFilter
0x180004966  call    cs:__imp_GetCurrentProcess
0x18000496c  mov     rcx, rax
0x18000496f  mov     edx, 0C0000409h
0x180004974  add     rsp, 20h
0x180004978  pop     rbx
0x180004979  jmp     cs:__imp_TerminateProcess
```
