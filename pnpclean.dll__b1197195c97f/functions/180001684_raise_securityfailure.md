# __raise_securityfailure

- ea: `0x180001684`
- end: `0x1800016b8`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800016c0`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001698`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001698`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000168f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000168f`
- `KERNEL32!GetCurrentProcess` at `0x18000169e`
- `KERNEL32!GetCurrentProcess` at `0x18000169e`
- `KERNEL32!TerminateProcess` at `0x1800016b1`

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
0x180001684  push    rbx
0x180001686  sub     rsp, 20h
0x18000168a  mov     rbx, rcx
0x18000168d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000168f  call    cs:__imp_SetUnhandledExceptionFilter
0x180001695  mov     rcx, rbx; ExceptionInfo
0x180001698  call    cs:__imp_UnhandledExceptionFilter
0x18000169e  call    cs:__imp_GetCurrentProcess
0x1800016a4  mov     rcx, rax
0x1800016a7  mov     edx, 0C0000409h
0x1800016ac  add     rsp, 20h
0x1800016b0  pop     rbx
0x1800016b1  jmp     cs:__imp_TerminateProcess
```
