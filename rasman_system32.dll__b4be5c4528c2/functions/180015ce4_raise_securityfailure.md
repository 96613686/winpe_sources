# __raise_securityfailure

- ea: `0x180015ce4`
- end: `0x180015d18`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180015d20`
- `0x180015ec8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015cfe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015cfe`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180015d11`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180015cef`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180015cef`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180015cf8`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180015cf8`

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
0x180015ce4  push    rbx
0x180015ce6  sub     rsp, 20h
0x180015cea  mov     rbx, rcx
0x180015ced  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180015cef  call    cs:__imp_SetUnhandledExceptionFilter
0x180015cf5  mov     rcx, rbx; ExceptionInfo
0x180015cf8  call    cs:__imp_UnhandledExceptionFilter
0x180015cfe  call    cs:__imp_GetCurrentProcess
0x180015d04  mov     rcx, rax
0x180015d07  mov     edx, 0C0000409h
0x180015d0c  add     rsp, 20h
0x180015d10  pop     rbx
0x180015d11  jmp     cs:__imp_TerminateProcess
```
