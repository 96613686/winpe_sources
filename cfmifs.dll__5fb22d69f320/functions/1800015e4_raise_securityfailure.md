# __raise_securityfailure

- ea: `0x1800015e4`
- end: `0x180001618`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001620`
- `0x1800017c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001611`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800015fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800015fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800015ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800015ef`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800015f8`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800015f8`

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
0x1800015e4  push    rbx
0x1800015e6  sub     rsp, 20h
0x1800015ea  mov     rbx, rcx
0x1800015ed  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800015ef  call    cs:__imp_SetUnhandledExceptionFilter
0x1800015f5  mov     rcx, rbx; ExceptionInfo
0x1800015f8  call    cs:__imp_UnhandledExceptionFilter
0x1800015fe  call    cs:__imp_GetCurrentProcess
0x180001604  mov     rcx, rax
0x180001607  mov     edx, 0C0000409h
0x18000160c  add     rsp, 20h
0x180001610  pop     rbx
0x180001611  jmp     cs:__imp_TerminateProcess
```
