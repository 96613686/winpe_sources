# __raise_securityfailure

- ea: `0x140002af0`
- end: `0x140002b24`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140002afb`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140002afb`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002b04`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002b04`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140002b1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002b0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002b0a`

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
0x140002af0  push    rbx
0x140002af2  sub     rsp, 20h
0x140002af6  mov     rbx, rcx
0x140002af9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140002afb  call    cs:__imp_SetUnhandledExceptionFilter
0x140002b01  mov     rcx, rbx; ExceptionInfo
0x140002b04  call    cs:__imp_UnhandledExceptionFilter
0x140002b0a  call    cs:__imp_GetCurrentProcess
0x140002b10  mov     rcx, rax
0x140002b13  mov     edx, 0C0000409h
0x140002b18  add     rsp, 20h
0x140002b1c  pop     rbx
0x140002b1d  jmp     cs:__imp_TerminateProcess
```
