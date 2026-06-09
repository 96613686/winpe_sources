# __raise_securityfailure

- ea: `0x1800019d4`
- end: `0x180001a08`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001a10`
- `0x180001bb8`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001a01`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800019df`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800019df`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800019e8`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800019e8`
- `KERNEL32!GetCurrentProcess` at `0x1800019ee`
- `KERNEL32!GetCurrentProcess` at `0x1800019ee`

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
0x1800019d4  push    rbx
0x1800019d6  sub     rsp, 20h
0x1800019da  mov     rbx, rcx
0x1800019dd  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800019df  call    cs:__imp_SetUnhandledExceptionFilter
0x1800019e5  mov     rcx, rbx; ExceptionInfo
0x1800019e8  call    cs:__imp_UnhandledExceptionFilter
0x1800019ee  call    cs:__imp_GetCurrentProcess
0x1800019f4  mov     rcx, rax
0x1800019f7  mov     edx, 0C0000409h
0x1800019fc  add     rsp, 20h
0x180001a00  pop     rbx
0x180001a01  jmp     cs:__imp_TerminateProcess
```
