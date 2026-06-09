# __raise_securityfailure

- ea: `0x180001a98`
- end: `0x180001acc`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001ae0`
- `0x180001c88`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001ac5`
- `KERNEL32!GetCurrentProcess` at `0x180001ab2`
- `KERNEL32!GetCurrentProcess` at `0x180001ab2`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001aa3`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001aa3`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001aac`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001aac`

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
0x180001a98  push    rbx
0x180001a9a  sub     rsp, 20h
0x180001a9e  mov     rbx, rcx
0x180001aa1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001aa3  call    cs:__imp_SetUnhandledExceptionFilter
0x180001aa9  mov     rcx, rbx; ExceptionInfo
0x180001aac  call    cs:__imp_UnhandledExceptionFilter
0x180001ab2  call    cs:__imp_GetCurrentProcess
0x180001ab8  mov     rcx, rax
0x180001abb  mov     edx, 0C0000409h
0x180001ac0  add     rsp, 20h
0x180001ac4  pop     rbx
0x180001ac5  jmp     cs:__imp_TerminateProcess
```
