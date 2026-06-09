# __raise_securityfailure

- ea: `0x18000a2bc`
- end: `0x18000a2f0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000a2c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000a2c7`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000a2d0`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000a2d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a2d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a2d6`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000a2e9`

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
0x18000a2bc  push    rbx
0x18000a2be  sub     rsp, 20h
0x18000a2c2  mov     rbx, rcx
0x18000a2c5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000a2c7  call    cs:__imp_SetUnhandledExceptionFilter
0x18000a2cd  mov     rcx, rbx; ExceptionInfo
0x18000a2d0  call    cs:__imp_UnhandledExceptionFilter
0x18000a2d6  call    cs:__imp_GetCurrentProcess
0x18000a2dc  mov     rcx, rax
0x18000a2df  mov     edx, 0C0000409h
0x18000a2e4  add     rsp, 20h
0x18000a2e8  pop     rbx
0x18000a2e9  jmp     cs:__imp_TerminateProcess
```
