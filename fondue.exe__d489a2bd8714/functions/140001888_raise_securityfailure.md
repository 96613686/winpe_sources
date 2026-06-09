# __raise_securityfailure

- ea: `0x140001888`
- end: `0x1400018bc`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400018d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400018b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400018a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400018a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001893`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001893`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x14000189c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x14000189c`

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
0x140001888  push    rbx
0x14000188a  sub     rsp, 20h
0x14000188e  mov     rbx, rcx
0x140001891  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001893  call    cs:__imp_SetUnhandledExceptionFilter
0x140001899  mov     rcx, rbx; ExceptionInfo
0x14000189c  call    cs:__imp_UnhandledExceptionFilter
0x1400018a2  call    cs:__imp_GetCurrentProcess
0x1400018a8  mov     rcx, rax
0x1400018ab  mov     edx, 0C0000409h
0x1400018b0  add     rsp, 20h
0x1400018b4  pop     rbx
0x1400018b5  jmp     cs:__imp_TerminateProcess
```
