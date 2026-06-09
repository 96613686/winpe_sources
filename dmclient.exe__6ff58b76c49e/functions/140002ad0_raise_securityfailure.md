# __raise_securityfailure

- ea: `0x140002ad0`
- end: `0x140002b04`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002b10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140002adb`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140002adb`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002ae4`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002ae4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002aea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002aea`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140002afd`

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
0x140002ad0  push    rbx
0x140002ad2  sub     rsp, 20h
0x140002ad6  mov     rbx, rcx
0x140002ad9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140002adb  call    cs:__imp_SetUnhandledExceptionFilter
0x140002ae1  mov     rcx, rbx; ExceptionInfo
0x140002ae4  call    cs:__imp_UnhandledExceptionFilter
0x140002aea  call    cs:__imp_GetCurrentProcess
0x140002af0  mov     rcx, rax
0x140002af3  mov     edx, 0C0000409h
0x140002af8  add     rsp, 20h
0x140002afc  pop     rbx
0x140002afd  jmp     cs:__imp_TerminateProcess
```
