# __raise_securityfailure

- ea: `0x180006998`
- end: `0x1800069cc`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800069e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800069ac`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800069ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800069a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800069a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800069b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800069b2`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800069c5`

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
0x180006998  push    rbx
0x18000699a  sub     rsp, 20h
0x18000699e  mov     rbx, rcx
0x1800069a1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800069a3  call    cs:__imp_SetUnhandledExceptionFilter
0x1800069a9  mov     rcx, rbx; ExceptionInfo
0x1800069ac  call    cs:__imp_UnhandledExceptionFilter
0x1800069b2  call    cs:__imp_GetCurrentProcess
0x1800069b8  mov     rcx, rax
0x1800069bb  mov     edx, 0C0000409h
0x1800069c0  add     rsp, 20h
0x1800069c4  pop     rbx
0x1800069c5  jmp     cs:__imp_TerminateProcess
```
