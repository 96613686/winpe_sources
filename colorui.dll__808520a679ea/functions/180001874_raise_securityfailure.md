# __raise_securityfailure

- ea: `0x180001874`
- end: `0x1800018a8`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800018b0`
- `0x180001a58`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18000188e`
- `KERNEL32!GetCurrentProcess` at `0x18000188e`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001888`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001888`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000187f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000187f`
- `KERNEL32!TerminateProcess` at `0x1800018a1`

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
0x180001874  push    rbx
0x180001876  sub     rsp, 20h
0x18000187a  mov     rbx, rcx
0x18000187d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000187f  call    cs:__imp_SetUnhandledExceptionFilter
0x180001885  mov     rcx, rbx; ExceptionInfo
0x180001888  call    cs:__imp_UnhandledExceptionFilter
0x18000188e  call    cs:__imp_GetCurrentProcess
0x180001894  mov     rcx, rax
0x180001897  mov     edx, 0C0000409h
0x18000189c  add     rsp, 20h
0x1800018a0  pop     rbx
0x1800018a1  jmp     cs:__imp_TerminateProcess
```
