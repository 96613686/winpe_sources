# __raise_securityfailure

- ea: `0x18000a424`
- end: `0x18000a458`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a460`
- `0x18000a608`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000a42f`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000a42f`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000a438`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000a438`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000a451`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a43e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a43e`

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
0x18000a424  push    rbx
0x18000a426  sub     rsp, 20h
0x18000a42a  mov     rbx, rcx
0x18000a42d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000a42f  call    cs:__imp_SetUnhandledExceptionFilter
0x18000a435  mov     rcx, rbx; ExceptionInfo
0x18000a438  call    cs:__imp_UnhandledExceptionFilter
0x18000a43e  call    cs:__imp_GetCurrentProcess
0x18000a444  mov     rcx, rax
0x18000a447  mov     edx, 0C0000409h
0x18000a44c  add     rsp, 20h
0x18000a450  pop     rbx
0x18000a451  jmp     cs:__imp_TerminateProcess
```
