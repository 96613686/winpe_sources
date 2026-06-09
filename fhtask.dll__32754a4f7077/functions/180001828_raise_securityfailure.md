# __raise_securityfailure

- ea: `0x180001828`
- end: `0x18000185c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001870`
- `0x180001a18`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x18000183c`
- `KERNEL32!UnhandledExceptionFilter` at `0x18000183c`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001833`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001833`
- `KERNEL32!GetCurrentProcess` at `0x180001842`
- `KERNEL32!GetCurrentProcess` at `0x180001842`
- `KERNEL32!TerminateProcess` at `0x180001855`

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
0x180001828  push    rbx
0x18000182a  sub     rsp, 20h
0x18000182e  mov     rbx, rcx
0x180001831  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001833  call    cs:__imp_SetUnhandledExceptionFilter
0x180001839  mov     rcx, rbx; ExceptionInfo
0x18000183c  call    cs:__imp_UnhandledExceptionFilter
0x180001842  call    cs:__imp_GetCurrentProcess
0x180001848  mov     rcx, rax
0x18000184b  mov     edx, 0C0000409h
0x180001850  add     rsp, 20h
0x180001854  pop     rbx
0x180001855  jmp     cs:__imp_TerminateProcess
```
