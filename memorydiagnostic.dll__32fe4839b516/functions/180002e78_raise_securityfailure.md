# __raise_securityfailure

- ea: `0x180002e78`
- end: `0x180002eac`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002ec0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180002e92`
- `KERNEL32!GetCurrentProcess` at `0x180002e92`
- `KERNEL32!UnhandledExceptionFilter` at `0x180002e8c`
- `KERNEL32!UnhandledExceptionFilter` at `0x180002e8c`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180002e83`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180002e83`
- `KERNEL32!TerminateProcess` at `0x180002ea5`

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
0x180002e78  push    rbx
0x180002e7a  sub     rsp, 20h
0x180002e7e  mov     rbx, rcx
0x180002e81  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180002e83  call    cs:__imp_SetUnhandledExceptionFilter
0x180002e89  mov     rcx, rbx; ExceptionInfo
0x180002e8c  call    cs:__imp_UnhandledExceptionFilter
0x180002e92  call    cs:__imp_GetCurrentProcess
0x180002e98  mov     rcx, rax
0x180002e9b  mov     edx, 0C0000409h
0x180002ea0  add     rsp, 20h
0x180002ea4  pop     rbx
0x180002ea5  jmp     cs:__imp_TerminateProcess
```
