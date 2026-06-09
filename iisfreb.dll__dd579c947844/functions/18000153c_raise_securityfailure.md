# __raise_securityfailure

- ea: `0x18000153c`
- end: `0x180001570`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001580`
- `0x180001728`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001550`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001550`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001547`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001547`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001556`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001556`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001569`

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
0x18000153c  push    rbx
0x18000153e  sub     rsp, 20h
0x180001542  mov     rbx, rcx
0x180001545  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001547  call    cs:__imp_SetUnhandledExceptionFilter
0x18000154d  mov     rcx, rbx; ExceptionInfo
0x180001550  call    cs:__imp_UnhandledExceptionFilter
0x180001556  call    cs:__imp_GetCurrentProcess
0x18000155c  mov     rcx, rax
0x18000155f  mov     edx, 0C0000409h
0x180001564  add     rsp, 20h
0x180001568  pop     rbx
0x180001569  jmp     cs:__imp_TerminateProcess
```
