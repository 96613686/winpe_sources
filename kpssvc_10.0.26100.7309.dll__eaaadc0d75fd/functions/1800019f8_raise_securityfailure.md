# __raise_securityfailure

- ea: `0x1800019f8`
- end: `0x180001a2c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001a40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001a03`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001a03`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001a0c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001a0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001a12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001a12`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001a25`

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
0x1800019f8  push    rbx
0x1800019fa  sub     rsp, 20h
0x1800019fe  mov     rbx, rcx
0x180001a01  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001a03  call    cs:__imp_SetUnhandledExceptionFilter
0x180001a09  mov     rcx, rbx; ExceptionInfo
0x180001a0c  call    cs:__imp_UnhandledExceptionFilter
0x180001a12  call    cs:__imp_GetCurrentProcess
0x180001a18  mov     rcx, rax
0x180001a1b  mov     edx, 0C0000409h
0x180001a20  add     rsp, 20h
0x180001a24  pop     rbx
0x180001a25  jmp     cs:__imp_TerminateProcess
```
