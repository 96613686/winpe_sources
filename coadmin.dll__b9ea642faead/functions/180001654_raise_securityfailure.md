# __raise_securityfailure

- ea: `0x180001654`
- end: `0x180001688`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001690`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001668`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001668`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000165f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000165f`
- `KERNEL32!TerminateProcess` at `0x180001681`
- `KERNEL32!GetCurrentProcess` at `0x18000166e`
- `KERNEL32!GetCurrentProcess` at `0x18000166e`

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
0x180001654  push    rbx
0x180001656  sub     rsp, 20h
0x18000165a  mov     rbx, rcx
0x18000165d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000165f  call    cs:__imp_SetUnhandledExceptionFilter
0x180001665  mov     rcx, rbx; ExceptionInfo
0x180001668  call    cs:__imp_UnhandledExceptionFilter
0x18000166e  call    cs:__imp_GetCurrentProcess
0x180001674  mov     rcx, rax
0x180001677  mov     edx, 0C0000409h
0x18000167c  add     rsp, 20h
0x180001680  pop     rbx
0x180001681  jmp     cs:__imp_TerminateProcess
```
