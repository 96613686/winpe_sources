# __raise_securityfailure

- ea: `0x180005818`
- end: `0x18000584c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180005860`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180005823`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180005823`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000582c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000582c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180005845`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005832`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005832`

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
0x180005818  push    rbx
0x18000581a  sub     rsp, 20h
0x18000581e  mov     rbx, rcx
0x180005821  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180005823  call    cs:__imp_SetUnhandledExceptionFilter
0x180005829  mov     rcx, rbx; ExceptionInfo
0x18000582c  call    cs:__imp_UnhandledExceptionFilter
0x180005832  call    cs:__imp_GetCurrentProcess
0x180005838  mov     rcx, rax
0x18000583b  mov     edx, 0C0000409h
0x180005840  add     rsp, 20h
0x180005844  pop     rbx
0x180005845  jmp     cs:__imp_TerminateProcess
```
