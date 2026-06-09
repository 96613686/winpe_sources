# __raise_securityfailure

- ea: `0x18000169c`
- end: `0x1800016d0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800016e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800016b0`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800016b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800016a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800016a7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800016c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800016b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800016b6`

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
0x18000169c  push    rbx
0x18000169e  sub     rsp, 20h
0x1800016a2  mov     rbx, rcx
0x1800016a5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800016a7  call    cs:__imp_SetUnhandledExceptionFilter
0x1800016ad  mov     rcx, rbx; ExceptionInfo
0x1800016b0  call    cs:__imp_UnhandledExceptionFilter
0x1800016b6  call    cs:__imp_GetCurrentProcess
0x1800016bc  mov     rcx, rax
0x1800016bf  mov     edx, 0C0000409h
0x1800016c4  add     rsp, 20h
0x1800016c8  pop     rbx
0x1800016c9  jmp     cs:__imp_TerminateProcess
```
