# __raise_securityfailure

- ea: `0x180001560`
- end: `0x180001594`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800015a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000156b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000156b`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001574`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001574`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000157a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000157a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000158d`

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
0x180001560  push    rbx
0x180001562  sub     rsp, 20h
0x180001566  mov     rbx, rcx
0x180001569  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000156b  call    cs:__imp_SetUnhandledExceptionFilter
0x180001571  mov     rcx, rbx; ExceptionInfo
0x180001574  call    cs:__imp_UnhandledExceptionFilter
0x18000157a  call    cs:__imp_GetCurrentProcess
0x180001580  mov     rcx, rax
0x180001583  mov     edx, 0C0000409h
0x180001588  add     rsp, 20h
0x18000158c  pop     rbx
0x18000158d  jmp     cs:__imp_TerminateProcess
```
