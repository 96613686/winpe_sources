# __raise_securityfailure

- ea: `0x18000221c`
- end: `0x180002250`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002260`
- `0x180002408`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002230`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002230`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002227`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002227`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002249`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002236`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002236`

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
0x18000221c  push    rbx
0x18000221e  sub     rsp, 20h
0x180002222  mov     rbx, rcx
0x180002225  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180002227  call    cs:__imp_SetUnhandledExceptionFilter
0x18000222d  mov     rcx, rbx; ExceptionInfo
0x180002230  call    cs:__imp_UnhandledExceptionFilter
0x180002236  call    cs:__imp_GetCurrentProcess
0x18000223c  mov     rcx, rax
0x18000223f  mov     edx, 0C0000409h
0x180002244  add     rsp, 20h
0x180002248  pop     rbx
0x180002249  jmp     cs:__imp_TerminateProcess
```
