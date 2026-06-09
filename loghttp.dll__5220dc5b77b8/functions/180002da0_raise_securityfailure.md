# __raise_securityfailure

- ea: `0x180002da0`
- end: `0x180002dd4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002de0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002dab`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002dab`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002db4`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002db4`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002dcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002dba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002dba`

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
0x180002da0  push    rbx
0x180002da2  sub     rsp, 20h
0x180002da6  mov     rbx, rcx
0x180002da9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180002dab  call    cs:__imp_SetUnhandledExceptionFilter
0x180002db1  mov     rcx, rbx; ExceptionInfo
0x180002db4  call    cs:__imp_UnhandledExceptionFilter
0x180002dba  call    cs:__imp_GetCurrentProcess
0x180002dc0  mov     rcx, rax
0x180002dc3  mov     edx, 0C0000409h
0x180002dc8  add     rsp, 20h
0x180002dcc  pop     rbx
0x180002dcd  jmp     cs:__imp_TerminateProcess
```
