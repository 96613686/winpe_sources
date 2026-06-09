# __raise_securityfailure

- ea: `0x140001684`
- end: `0x1400016b8`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400016c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400016b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000169e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000169e`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001698`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001698`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000168f`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000168f`

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
0x140001684  push    rbx
0x140001686  sub     rsp, 20h
0x14000168a  mov     rbx, rcx
0x14000168d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14000168f  call    cs:__imp_SetUnhandledExceptionFilter
0x140001695  mov     rcx, rbx; ExceptionInfo
0x140001698  call    cs:__imp_UnhandledExceptionFilter
0x14000169e  call    cs:__imp_GetCurrentProcess
0x1400016a4  mov     rcx, rax
0x1400016a7  mov     edx, 0C0000409h
0x1400016ac  add     rsp, 20h
0x1400016b0  pop     rbx
0x1400016b1  jmp     cs:__imp_TerminateProcess
```
