# __raise_securityfailure

- ea: `0x18000195c`
- end: `0x180001990`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800019a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001989`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001976`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001976`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001970`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001970`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001967`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001967`

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
0x18000195c  push    rbx
0x18000195e  sub     rsp, 20h
0x180001962  mov     rbx, rcx
0x180001965  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001967  call    cs:__imp_SetUnhandledExceptionFilter
0x18000196d  mov     rcx, rbx; ExceptionInfo
0x180001970  call    cs:__imp_UnhandledExceptionFilter
0x180001976  call    cs:__imp_GetCurrentProcess
0x18000197c  mov     rcx, rax
0x18000197f  mov     edx, 0C0000409h
0x180001984  add     rsp, 20h
0x180001988  pop     rbx
0x180001989  jmp     cs:__imp_TerminateProcess
```
