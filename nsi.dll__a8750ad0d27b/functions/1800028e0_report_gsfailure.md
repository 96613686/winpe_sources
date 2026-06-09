# __report_gsfailure

- ea: `0x1800028e0`
- end: `0x180002a57`
- name: `__report_gsfailure`
- size: `375`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003120`

## callees

- `0x1800028e0`
- `0x180002b10`
- `0x180002b1c`
- `0x180002b28`
- `0x180002b34`
- `0x180002b40`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  struct _RUNTIME_FUNCTION *FunctionEntry; // [rsp+40h] [rbp-48h]
  DWORD64 ControlPc; // [rsp+48h] [rbp-40h]
  unsigned __int64 ImageBase; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+58h] [rbp-30h] BYREF
  PVOID HandlerData[5]; // [rsp+60h] [rbp-28h] BYREF
  DWORD64 retaddr; // [rsp+88h] [rbp+0h]
  uintptr_t v7; // [rsp+90h] [rbp+8h] BYREF

  v7 = StackCookie;
  EstablisherFrame = 0;
  HandlerData[0] = 0;
  ImageBase = 0;
  RtlCaptureContext_0(&ContextRecord);
  ControlPc = ContextRecord.Rip;
  FunctionEntry = RtlLookupFunctionEntry_0(ContextRecord.Rip, &ImageBase, 0);
  if ( FunctionEntry )
  {
    RtlVirtualUnwind_0(0, ImageBase, ControlPc, FunctionEntry, &ContextRecord, HandlerData, &EstablisherFrame, 0);
  }
  else
  {
    ContextRecord.Rip = retaddr;
    ContextRecord.Rsp = (DWORD64)&v7;
  }
  qword_180006030 = ContextRecord.Rip;
  ContextRecord.Rcx = v7;
  dword_180006020 = -1073740791;
  dword_180006024 = 1;
  dword_180006038 = 1;
  qword_180006040[0] = 2;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  RtlUnhandledExceptionFilter_0((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
  NtTerminateProcess_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, -1073740791);
}

```

## disassembly

```asm
0x1800028e0  mov     [rsp+arg_0], rcx
0x1800028e5  sub     rsp, 88h
0x1800028ec  mov     [rsp+88h+ControlPc], 0
0x1800028f5  mov     [rsp+88h+var_30], 0
0x1800028fe  mov     [rsp+88h+FunctionEntry], 0
0x180002907  mov     [rsp+88h+var_28], 0
0x180002910  mov     [rsp+88h+ImageBase], 0
0x180002919  lea     rcx, ContextRecord; ContextRecord
0x180002920  call    RtlCaptureContext_0
0x180002925  mov     rax, cs:ContextRecord.Rip
0x18000292c  mov     [rsp+88h+ControlPc], rax
0x180002931  xor     r8d, r8d; HistoryTable
0x180002934  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x180002939  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000293e  call    RtlLookupFunctionEntry_0
0x180002943  mov     [rsp+88h+FunctionEntry], rax
0x180002948  cmp     [rsp+88h+FunctionEntry], 0
0x18000294e  jz      short loc_180002992
0x180002950  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x180002959  lea     rax, [rsp+88h+var_30]
0x18000295e  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180002963  lea     rax, [rsp+88h+var_28]
0x180002968  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000296d  lea     rax, ContextRecord
0x180002974  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x180002979  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x18000297e  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180002983  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x180002988  xor     ecx, ecx; HandlerType
0x18000298a  call    RtlVirtualUnwind_0
0x18000298f  nop
0x180002990  jmp     short loc_1800029B4
0x180002992  mov     rax, [rsp+88h]
0x18000299a  mov     cs:ContextRecord.Rip, rax
0x1800029a1  lea     rax, [rsp+88h]
0x1800029a9  add     rax, 8
0x1800029ad  mov     cs:ContextRecord.Rsp, rax
0x1800029b4  mov     rax, cs:ContextRecord.Rip
0x1800029bb  mov     cs:qword_180006030, rax
0x1800029c2  mov     rax, [rsp+88h+arg_0]
0x1800029ca  mov     cs:ContextRecord.Rcx, rax
0x1800029d1  mov     cs:dword_180006020, 0C0000409h
0x1800029db  mov     cs:dword_180006024, 1
0x1800029e5  mov     cs:dword_180006038, 1
0x1800029ef  mov     eax, 8
0x1800029f4  imul    rax, 0
0x1800029f8  lea     rcx, qword_180006040
0x1800029ff  mov     qword ptr [rcx+rax], 2
0x180002a07  mov     eax, 8
0x180002a0c  imul    rax, 0
0x180002a10  mov     rcx, cs:__security_cookie
0x180002a17  mov     [rsp+rax+88h+var_20], rcx
0x180002a1c  mov     eax, 8
0x180002a21  imul    rax, 1
0x180002a25  mov     rcx, cs:__security_cookie_complement
0x180002a2c  mov     [rsp+rax+88h+var_20], rcx
0x180002a31  lea     rcx, ExceptionInfo; ExceptionInfo
0x180002a38  call    RtlUnhandledExceptionFilter_0
0x180002a3d  mov     edx, 0C0000409h; ExitStatus
0x180002a42  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180002a49  call    NtTerminateProcess_0
0x180002a4e  nop
0x180002a4f  add     rsp, 88h
0x180002a56  retn
```
