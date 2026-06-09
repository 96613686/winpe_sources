# __raise_securityfailure

- ea: `0x180002f08`
- end: `0x180002f3c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002f50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002f1c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002f1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002f13`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002f13`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002f35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002f22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002f22`

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
0x180002f08  push    rbx
0x180002f0a  sub     rsp, 20h
0x180002f0e  mov     rbx, rcx
0x180002f11  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180002f13  call    cs:__imp_SetUnhandledExceptionFilter
0x180002f19  mov     rcx, rbx; ExceptionInfo
0x180002f1c  call    cs:__imp_UnhandledExceptionFilter
0x180002f22  call    cs:__imp_GetCurrentProcess
0x180002f28  mov     rcx, rax
0x180002f2b  mov     edx, 0C0000409h
0x180002f30  add     rsp, 20h
0x180002f34  pop     rbx
0x180002f35  jmp     cs:__imp_TerminateProcess
```
