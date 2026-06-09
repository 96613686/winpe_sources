# __raise_securityfailure

- ea: `0x14000272c`
- end: `0x140002760`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002770`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140002759`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002746`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002746`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002740`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002740`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140002737`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140002737`

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
0x14000272c  push    rbx
0x14000272e  sub     rsp, 20h
0x140002732  mov     rbx, rcx
0x140002735  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140002737  call    cs:__imp_SetUnhandledExceptionFilter
0x14000273d  mov     rcx, rbx; ExceptionInfo
0x140002740  call    cs:__imp_UnhandledExceptionFilter
0x140002746  call    cs:__imp_GetCurrentProcess
0x14000274c  mov     rcx, rax
0x14000274f  mov     edx, 0C0000409h
0x140002754  add     rsp, 20h
0x140002758  pop     rbx
0x140002759  jmp     cs:__imp_TerminateProcess
```
