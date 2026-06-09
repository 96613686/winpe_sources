# __report_gsfailure

- ea: `0x140001430`
- end: `0x1400015a7`
- name: `__report_gsfailure`
- size: `375`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001820`

## callees

- `0x140001430`
- `0x140001660`
- `0x14000166c`
- `0x140001678`
- `0x140001684`
- `0x140001690`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  struct _RUNTIME_FUNCTION *FunctionEntry; // [rsp+40h] [rbp-48h]
  unsigned __int64 ControlPc; // [rsp+48h] [rbp-40h]
  unsigned __int64 ImageBase; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+58h] [rbp-30h] BYREF
  PVOID HandlerData[5]; // [rsp+60h] [rbp-28h] BYREF
  unsigned __int64 retaddr; // [rsp+88h] [rbp+0h]
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
    ContextRecord.Rsp = (unsigned __int64)&v7;
  }
  qword_140003030 = ContextRecord.Rip;
  ContextRecord.Rcx = v7;
  dword_140003020 = -1073740791;
  dword_140003024 = 1;
  dword_140003038 = 1;
  qword_140003040[0] = 2;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  RtlUnhandledExceptionFilter_0((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
  NtTerminateProcess_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, -1073740791);
}

```

## disassembly

```asm
0x140001430  mov     [rsp+arg_0], rcx
0x140001435  sub     rsp, 88h
0x14000143c  mov     [rsp+88h+ControlPc], 0
0x140001445  mov     [rsp+88h+var_30], 0
0x14000144e  mov     [rsp+88h+FunctionEntry], 0
0x140001457  mov     [rsp+88h+var_28], 0
0x140001460  mov     [rsp+88h+ImageBase], 0
0x140001469  lea     rcx, ContextRecord; ContextRecord
0x140001470  call    RtlCaptureContext_0
0x140001475  mov     rax, cs:ContextRecord.Rip
0x14000147c  mov     [rsp+88h+ControlPc], rax
0x140001481  xor     r8d, r8d; HistoryTable
0x140001484  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x140001489  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x14000148e  call    RtlLookupFunctionEntry_0
0x140001493  mov     [rsp+88h+FunctionEntry], rax
0x140001498  cmp     [rsp+88h+FunctionEntry], 0
0x14000149e  jz      short loc_1400014E2
0x1400014a0  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1400014a9  lea     rax, [rsp+88h+var_30]
0x1400014ae  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1400014b3  lea     rax, [rsp+88h+var_28]
0x1400014b8  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1400014bd  lea     rax, ContextRecord
0x1400014c4  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1400014c9  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1400014ce  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1400014d3  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1400014d8  xor     ecx, ecx; HandlerType
0x1400014da  call    RtlVirtualUnwind_0
0x1400014df  nop
0x1400014e0  jmp     short loc_140001504
0x1400014e2  mov     rax, [rsp+88h]
0x1400014ea  mov     cs:ContextRecord.Rip, rax
0x1400014f1  lea     rax, [rsp+88h]
0x1400014f9  add     rax, 8
0x1400014fd  mov     cs:ContextRecord.Rsp, rax
0x140001504  mov     rax, cs:ContextRecord.Rip
0x14000150b  mov     cs:qword_140003030, rax
0x140001512  mov     rax, [rsp+88h+arg_0]
0x14000151a  mov     cs:ContextRecord.Rcx, rax
0x140001521  mov     cs:dword_140003020, 0C0000409h
0x14000152b  mov     cs:dword_140003024, 1
0x140001535  mov     cs:dword_140003038, 1
0x14000153f  mov     eax, 8
0x140001544  imul    rax, 0
0x140001548  lea     rcx, qword_140003040
0x14000154f  mov     qword ptr [rcx+rax], 2
0x140001557  mov     eax, 8
0x14000155c  imul    rax, 0
0x140001560  mov     rcx, cs:__security_cookie
0x140001567  mov     [rsp+rax+88h+var_20], rcx
0x14000156c  mov     eax, 8
0x140001571  imul    rax, 1
0x140001575  mov     rcx, cs:__security_cookie_complement
0x14000157c  mov     [rsp+rax+88h+var_20], rcx
0x140001581  lea     rcx, ExceptionInfo; ExceptionInfo
0x140001588  call    RtlUnhandledExceptionFilter_0
0x14000158d  mov     edx, 0C0000409h; ExitStatus
0x140001592  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140001599  call    NtTerminateProcess_0
0x14000159e  nop
0x14000159f  add     rsp, 88h
0x1400015a6  retn
```
