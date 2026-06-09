# __raise_securityfailure

- ea: `0x18000183c`
- end: `0x180001870`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001880`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001847`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001847`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001850`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001850`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001856`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001856`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001869`

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
0x18000183c  push    rbx
0x18000183e  sub     rsp, 20h
0x180001842  mov     rbx, rcx
0x180001845  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001847  call    cs:__imp_SetUnhandledExceptionFilter
0x18000184d  mov     rcx, rbx; ExceptionInfo
0x180001850  call    cs:__imp_UnhandledExceptionFilter
0x180001856  call    cs:__imp_GetCurrentProcess
0x18000185c  mov     rcx, rax
0x18000185f  mov     edx, 0C0000409h
0x180001864  add     rsp, 20h
0x180001868  pop     rbx
0x180001869  jmp     cs:__imp_TerminateProcess
```
