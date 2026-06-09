# __raise_securityfailure

- ea: `0x1400014e8`
- end: `0x14000151c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001530`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x140001515`
- `KERNEL32!GetCurrentProcess` at `0x140001502`
- `KERNEL32!GetCurrentProcess` at `0x140001502`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400014f3`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400014f3`
- `KERNEL32!UnhandledExceptionFilter` at `0x1400014fc`
- `KERNEL32!UnhandledExceptionFilter` at `0x1400014fc`

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
0x1400014e8  push    rbx
0x1400014ea  sub     rsp, 20h
0x1400014ee  mov     rbx, rcx
0x1400014f1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1400014f3  call    cs:__imp_SetUnhandledExceptionFilter
0x1400014f9  mov     rcx, rbx; ExceptionInfo
0x1400014fc  call    cs:__imp_UnhandledExceptionFilter
0x140001502  call    cs:__imp_GetCurrentProcess
0x140001508  mov     rcx, rax
0x14000150b  mov     edx, 0C0000409h
0x140001510  add     rsp, 20h
0x140001514  pop     rbx
0x140001515  jmp     cs:__imp_TerminateProcess
```
