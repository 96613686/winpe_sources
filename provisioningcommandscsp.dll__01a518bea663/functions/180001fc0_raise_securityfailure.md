# __raise_securityfailure

- ea: `0x180001fc0`
- end: `0x180001ff4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002000`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001fcb`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001fcb`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001fd4`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001fd4`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001fed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001fda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001fda`

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
0x180001fc0  push    rbx
0x180001fc2  sub     rsp, 20h
0x180001fc6  mov     rbx, rcx
0x180001fc9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001fcb  call    cs:__imp_SetUnhandledExceptionFilter
0x180001fd1  mov     rcx, rbx; ExceptionInfo
0x180001fd4  call    cs:__imp_UnhandledExceptionFilter
0x180001fda  call    cs:__imp_GetCurrentProcess
0x180001fe0  mov     rcx, rax
0x180001fe3  mov     edx, 0C0000409h
0x180001fe8  add     rsp, 20h
0x180001fec  pop     rbx
0x180001fed  jmp     cs:__imp_TerminateProcess
```
