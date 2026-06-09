# __raise_securityfailure

- ea: `0x180001bd8`
- end: `0x180001c0c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001c20`
- `0x180001dc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001be3`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001be3`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001bec`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001bec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001bf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001bf2`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001c05`

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
0x180001bd8  push    rbx
0x180001bda  sub     rsp, 20h
0x180001bde  mov     rbx, rcx
0x180001be1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001be3  call    cs:__imp_SetUnhandledExceptionFilter
0x180001be9  mov     rcx, rbx; ExceptionInfo
0x180001bec  call    cs:__imp_UnhandledExceptionFilter
0x180001bf2  call    cs:__imp_GetCurrentProcess
0x180001bf8  mov     rcx, rax
0x180001bfb  mov     edx, 0C0000409h
0x180001c00  add     rsp, 20h
0x180001c04  pop     rbx
0x180001c05  jmp     cs:__imp_TerminateProcess
```
