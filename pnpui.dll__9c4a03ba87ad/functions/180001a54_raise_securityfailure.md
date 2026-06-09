# __raise_securityfailure

- ea: `0x180001a54`
- end: `0x180001a88`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001a90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001a68`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001a68`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001a5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001a5f`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001a81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001a6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001a6e`

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
0x180001a54  push    rbx
0x180001a56  sub     rsp, 20h
0x180001a5a  mov     rbx, rcx
0x180001a5d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001a5f  call    cs:__imp_SetUnhandledExceptionFilter
0x180001a65  mov     rcx, rbx; ExceptionInfo
0x180001a68  call    cs:__imp_UnhandledExceptionFilter
0x180001a6e  call    cs:__imp_GetCurrentProcess
0x180001a74  mov     rcx, rax
0x180001a77  mov     edx, 0C0000409h
0x180001a7c  add     rsp, 20h
0x180001a80  pop     rbx
0x180001a81  jmp     cs:__imp_TerminateProcess
```
