# __raise_securityfailure

- ea: `0x180001bb0`
- end: `0x180001be4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001bf0`
- `0x180001d98`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001bc4`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001bc4`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001bbb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001bbb`
- `KERNEL32!GetCurrentProcess` at `0x180001bca`
- `KERNEL32!GetCurrentProcess` at `0x180001bca`
- `KERNEL32!TerminateProcess` at `0x180001bdd`

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
0x180001bb0  push    rbx
0x180001bb2  sub     rsp, 20h
0x180001bb6  mov     rbx, rcx
0x180001bb9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001bbb  call    cs:__imp_SetUnhandledExceptionFilter
0x180001bc1  mov     rcx, rbx; ExceptionInfo
0x180001bc4  call    cs:__imp_UnhandledExceptionFilter
0x180001bca  call    cs:__imp_GetCurrentProcess
0x180001bd0  mov     rcx, rax
0x180001bd3  mov     edx, 0C0000409h
0x180001bd8  add     rsp, 20h
0x180001bdc  pop     rbx
0x180001bdd  jmp     cs:__imp_TerminateProcess
```
