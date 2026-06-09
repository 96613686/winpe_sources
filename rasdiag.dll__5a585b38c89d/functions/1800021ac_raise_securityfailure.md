# __raise_securityfailure

- ea: `0x1800021ac`
- end: `0x1800021e0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800021f0`
- `0x180002398`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x1800021d9`
- `KERNEL32!GetCurrentProcess` at `0x1800021c6`
- `KERNEL32!GetCurrentProcess` at `0x1800021c6`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800021b7`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800021b7`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800021c0`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800021c0`

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
0x1800021ac  push    rbx
0x1800021ae  sub     rsp, 20h
0x1800021b2  mov     rbx, rcx
0x1800021b5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800021b7  call    cs:__imp_SetUnhandledExceptionFilter
0x1800021bd  mov     rcx, rbx; ExceptionInfo
0x1800021c0  call    cs:__imp_UnhandledExceptionFilter
0x1800021c6  call    cs:__imp_GetCurrentProcess
0x1800021cc  mov     rcx, rax
0x1800021cf  mov     edx, 0C0000409h
0x1800021d4  add     rsp, 20h
0x1800021d8  pop     rbx
0x1800021d9  jmp     cs:__imp_TerminateProcess
```
