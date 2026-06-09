# __raise_securityfailure

- ea: `0x180001528`
- end: `0x18000155c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001570`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000153c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000153c`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001533`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001533`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001555`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001542`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001542`

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
0x180001528  push    rbx
0x18000152a  sub     rsp, 20h
0x18000152e  mov     rbx, rcx
0x180001531  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001533  call    cs:__imp_SetUnhandledExceptionFilter
0x180001539  mov     rcx, rbx; ExceptionInfo
0x18000153c  call    cs:__imp_UnhandledExceptionFilter
0x180001542  call    cs:__imp_GetCurrentProcess
0x180001548  mov     rcx, rax
0x18000154b  mov     edx, 0C0000409h
0x180001550  add     rsp, 20h
0x180001554  pop     rbx
0x180001555  jmp     cs:__imp_TerminateProcess
```
