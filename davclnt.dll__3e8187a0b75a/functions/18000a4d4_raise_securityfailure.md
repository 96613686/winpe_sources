# __raise_securityfailure

- ea: `0x18000a4d4`
- end: `0x18000a508`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000a4df`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000a4df`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000a4e8`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000a4e8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000a501`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a4ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a4ee`

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
0x18000a4d4  push    rbx
0x18000a4d6  sub     rsp, 20h
0x18000a4da  mov     rbx, rcx
0x18000a4dd  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000a4df  call    cs:__imp_SetUnhandledExceptionFilter
0x18000a4e5  mov     rcx, rbx; ExceptionInfo
0x18000a4e8  call    cs:__imp_UnhandledExceptionFilter
0x18000a4ee  call    cs:__imp_GetCurrentProcess
0x18000a4f4  mov     rcx, rax
0x18000a4f7  mov     edx, 0C0000409h
0x18000a4fc  add     rsp, 20h
0x18000a500  pop     rbx
0x18000a501  jmp     cs:__imp_TerminateProcess
```
