# __raise_securityfailure

- ea: `0x180005f9c`
- end: `0x180005fd0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180005fe0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180005fc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005fb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005fb6`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180005fb0`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180005fb0`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180005fa7`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180005fa7`

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
0x180005f9c  push    rbx
0x180005f9e  sub     rsp, 20h
0x180005fa2  mov     rbx, rcx
0x180005fa5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180005fa7  call    cs:__imp_SetUnhandledExceptionFilter
0x180005fad  mov     rcx, rbx; ExceptionInfo
0x180005fb0  call    cs:__imp_UnhandledExceptionFilter
0x180005fb6  call    cs:__imp_GetCurrentProcess
0x180005fbc  mov     rcx, rax
0x180005fbf  mov     edx, 0C0000409h
0x180005fc4  add     rsp, 20h
0x180005fc8  pop     rbx
0x180005fc9  jmp     cs:__imp_TerminateProcess
```
