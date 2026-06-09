# __raise_securityfailure

- ea: `0x1800057ac`
- end: `0x1800057e0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800057f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800057c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800057c6`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800057d9`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800057c0`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800057c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800057b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800057b7`

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
0x1800057ac  push    rbx
0x1800057ae  sub     rsp, 20h
0x1800057b2  mov     rbx, rcx
0x1800057b5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800057b7  call    cs:__imp_SetUnhandledExceptionFilter
0x1800057bd  mov     rcx, rbx; ExceptionInfo
0x1800057c0  call    cs:__imp_UnhandledExceptionFilter
0x1800057c6  call    cs:__imp_GetCurrentProcess
0x1800057cc  mov     rcx, rax
0x1800057cf  mov     edx, 0C0000409h
0x1800057d4  add     rsp, 20h
0x1800057d8  pop     rbx
0x1800057d9  jmp     cs:__imp_TerminateProcess
```
