# __raise_securityfailure

- ea: `0x140001b78`
- end: `0x140001bac`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001bc0`
- `0x140001d68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140001ba5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001b92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001b92`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001b8c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001b8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001b83`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001b83`

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
0x140001b78  push    rbx
0x140001b7a  sub     rsp, 20h
0x140001b7e  mov     rbx, rcx
0x140001b81  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001b83  call    cs:__imp_SetUnhandledExceptionFilter
0x140001b89  mov     rcx, rbx; ExceptionInfo
0x140001b8c  call    cs:__imp_UnhandledExceptionFilter
0x140001b92  call    cs:__imp_GetCurrentProcess
0x140001b98  mov     rcx, rax
0x140001b9b  mov     edx, 0C0000409h
0x140001ba0  add     rsp, 20h
0x140001ba4  pop     rbx
0x140001ba5  jmp     cs:__imp_TerminateProcess
```
