# __raise_securityfailure

- ea: `0x180001f10`
- end: `0x180001f44`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001f50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001f2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001f2a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001f3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001f1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001f1b`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001f24`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001f24`

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
0x180001f10  push    rbx
0x180001f12  sub     rsp, 20h
0x180001f16  mov     rbx, rcx
0x180001f19  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001f1b  call    cs:__imp_SetUnhandledExceptionFilter
0x180001f21  mov     rcx, rbx; ExceptionInfo
0x180001f24  call    cs:__imp_UnhandledExceptionFilter
0x180001f2a  call    cs:__imp_GetCurrentProcess
0x180001f30  mov     rcx, rax
0x180001f33  mov     edx, 0C0000409h
0x180001f38  add     rsp, 20h
0x180001f3c  pop     rbx
0x180001f3d  jmp     cs:__imp_TerminateProcess
```
