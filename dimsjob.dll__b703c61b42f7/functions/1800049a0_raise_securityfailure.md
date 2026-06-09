# __raise_securityfailure

- ea: `0x1800049a0`
- end: `0x1800049d4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800049e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800049cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800049ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800049ba`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800049b4`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800049b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800049ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800049ab`

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
0x1800049a0  push    rbx
0x1800049a2  sub     rsp, 20h
0x1800049a6  mov     rbx, rcx
0x1800049a9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800049ab  call    cs:__imp_SetUnhandledExceptionFilter
0x1800049b1  mov     rcx, rbx; ExceptionInfo
0x1800049b4  call    cs:__imp_UnhandledExceptionFilter
0x1800049ba  call    cs:__imp_GetCurrentProcess
0x1800049c0  mov     rcx, rax
0x1800049c3  mov     edx, 0C0000409h
0x1800049c8  add     rsp, 20h
0x1800049cc  pop     rbx
0x1800049cd  jmp     cs:__imp_TerminateProcess
```
