# __raise_securityfailure

- ea: `0x1800016cc`
- end: `0x180001700`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001710`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800016f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800016e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800016e6`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800016e0`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800016e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800016d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800016d7`

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
0x1800016cc  push    rbx
0x1800016ce  sub     rsp, 20h
0x1800016d2  mov     rbx, rcx
0x1800016d5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800016d7  call    cs:__imp_SetUnhandledExceptionFilter
0x1800016dd  mov     rcx, rbx; ExceptionInfo
0x1800016e0  call    cs:__imp_UnhandledExceptionFilter
0x1800016e6  call    cs:__imp_GetCurrentProcess
0x1800016ec  mov     rcx, rax
0x1800016ef  mov     edx, 0C0000409h
0x1800016f4  add     rsp, 20h
0x1800016f8  pop     rbx
0x1800016f9  jmp     cs:__imp_TerminateProcess
```
