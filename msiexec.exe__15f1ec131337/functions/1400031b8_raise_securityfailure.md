# __raise_securityfailure

- ea: `0x1400031b8`
- end: `0x1400031ec`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140003200`
- `0x1400033a8`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1400031d2`
- `KERNEL32!GetCurrentProcess` at `0x1400031d2`
- `KERNEL32!UnhandledExceptionFilter` at `0x1400031cc`
- `KERNEL32!UnhandledExceptionFilter` at `0x1400031cc`
- `KERNEL32!TerminateProcess` at `0x1400031e5`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400031c3`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400031c3`

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
0x1400031b8  push    rbx
0x1400031ba  sub     rsp, 20h
0x1400031be  mov     rbx, rcx
0x1400031c1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1400031c3  call    cs:__imp_SetUnhandledExceptionFilter
0x1400031c9  mov     rcx, rbx; ExceptionInfo
0x1400031cc  call    cs:__imp_UnhandledExceptionFilter
0x1400031d2  call    cs:__imp_GetCurrentProcess
0x1400031d8  mov     rcx, rax
0x1400031db  mov     edx, 0C0000409h
0x1400031e0  add     rsp, 20h
0x1400031e4  pop     rbx
0x1400031e5  jmp     cs:__imp_TerminateProcess
```
