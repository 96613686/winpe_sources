# __raise_securityfailure

- ea: `0x18001d25c`
- end: `0x18001d290`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001d2a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18001d267`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18001d267`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18001d270`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18001d270`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d276`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d276`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18001d289`

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
0x18001d25c  push    rbx
0x18001d25e  sub     rsp, 20h
0x18001d262  mov     rbx, rcx
0x18001d265  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18001d267  call    cs:__imp_SetUnhandledExceptionFilter
0x18001d26d  mov     rcx, rbx; ExceptionInfo
0x18001d270  call    cs:__imp_UnhandledExceptionFilter
0x18001d276  call    cs:__imp_GetCurrentProcess
0x18001d27c  mov     rcx, rax
0x18001d27f  mov     edx, 0C0000409h
0x18001d284  add     rsp, 20h
0x18001d288  pop     rbx
0x18001d289  jmp     cs:__imp_TerminateProcess
```
