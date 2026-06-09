# __raise_securityfailure

- ea: `0x180005498`
- end: `0x1800054cc`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800054e0`
- `0x180005688`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800054a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800054a3`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800054ac`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800054ac`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800054c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800054b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800054b2`

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
0x180005498  push    rbx
0x18000549a  sub     rsp, 20h
0x18000549e  mov     rbx, rcx
0x1800054a1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800054a3  call    cs:__imp_SetUnhandledExceptionFilter
0x1800054a9  mov     rcx, rbx; ExceptionInfo
0x1800054ac  call    cs:__imp_UnhandledExceptionFilter
0x1800054b2  call    cs:__imp_GetCurrentProcess
0x1800054b8  mov     rcx, rax
0x1800054bb  mov     edx, 0C0000409h
0x1800054c0  add     rsp, 20h
0x1800054c4  pop     rbx
0x1800054c5  jmp     cs:__imp_TerminateProcess
```
