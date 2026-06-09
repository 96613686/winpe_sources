# __raise_securityfailure

- ea: `0x1800019e8`
- end: `0x180001a1c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001a30`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001a15`
- `KERNEL32!GetCurrentProcess` at `0x180001a02`
- `KERNEL32!GetCurrentProcess` at `0x180001a02`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800019f3`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800019f3`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800019fc`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800019fc`

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
0x1800019e8  push    rbx
0x1800019ea  sub     rsp, 20h
0x1800019ee  mov     rbx, rcx
0x1800019f1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800019f3  call    cs:__imp_SetUnhandledExceptionFilter
0x1800019f9  mov     rcx, rbx; ExceptionInfo
0x1800019fc  call    cs:__imp_UnhandledExceptionFilter
0x180001a02  call    cs:__imp_GetCurrentProcess
0x180001a08  mov     rcx, rax
0x180001a0b  mov     edx, 0C0000409h
0x180001a10  add     rsp, 20h
0x180001a14  pop     rbx
0x180001a15  jmp     cs:__imp_TerminateProcess
```
