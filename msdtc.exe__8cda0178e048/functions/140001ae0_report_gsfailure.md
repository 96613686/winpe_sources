# __report_gsfailure

- ea: `0x140001ae0`
- end: `0x140001c80`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006f10`

## callees

- `0x140001a98`
- `0x140001ae0`

## import_xrefs

- `ntdll!RtlVirtualUnwind` at `0x140001b8c`
- `ntdll!RtlVirtualUnwind` at `0x140001b8c`
- `ntdll!RtlLookupFunctionEntry` at `0x140001b3f`
- `ntdll!RtlLookupFunctionEntry` at `0x140001b3f`
- `ntdll!RtlCaptureContext` at `0x140001b20`
- `ntdll!RtlCaptureContext` at `0x140001b20`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  struct _RUNTIME_FUNCTION *FunctionEntry; // [rsp+40h] [rbp-48h]
  DWORD64 ControlPc; // [rsp+48h] [rbp-40h]
  unsigned __int64 ImageBase; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+58h] [rbp-30h] BYREF
  PVOID HandlerData[5]; // [rsp+60h] [rbp-28h] BYREF

  EstablisherFrame = 0;
  HandlerData[0] = 0;
  ImageBase = 0;
  RtlCaptureContext(&ContextRecord);
  ControlPc = ContextRecord.Rip;
  FunctionEntry = RtlLookupFunctionEntry(ContextRecord.Rip, &ImageBase, 0);
  if ( FunctionEntry )
  {
    RtlVirtualUnwind(0, ImageBase, ControlPc, FunctionEntry, &ContextRecord, HandlerData, &EstablisherFrame, 0);
  }
  else
  {
    ContextRecord.Rip = *(_QWORD *)ContextRecord.Rsp;
    ContextRecord.Rsp += 8LL;
  }
  qword_14000E370 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_14000E360 = -1073740791;
  dword_14000E364 = 1;
  dword_14000E378 = 3;
  qword_14000E380[0] = 2;
  qword_14000E380[1] = _security_cookie;
  qword_14000E380[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x140001ae0  mov     [rsp+arg_0], rcx
0x140001ae5  sub     rsp, 88h
0x140001aec  mov     [rsp+88h+ControlPc], 0
0x140001af5  mov     [rsp+88h+var_30], 0
0x140001afe  mov     [rsp+88h+FunctionEntry], 0
0x140001b07  mov     [rsp+88h+var_28], 0
0x140001b10  mov     [rsp+88h+ImageBase], 0
0x140001b19  lea     rcx, ContextRecord; ContextRecord
0x140001b20  call    cs:__imp_RtlCaptureContext
0x140001b26  mov     rax, cs:ContextRecord.Rip
0x140001b2d  mov     [rsp+88h+ControlPc], rax
0x140001b32  xor     r8d, r8d; HistoryTable
0x140001b35  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x140001b3a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x140001b3f  call    cs:__imp_RtlLookupFunctionEntry
0x140001b45  mov     [rsp+88h+FunctionEntry], rax
0x140001b4a  cmp     [rsp+88h+FunctionEntry], 0
0x140001b50  jz      short loc_140001B95
0x140001b52  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x140001b5b  lea     rax, [rsp+88h+var_30]
0x140001b60  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x140001b65  lea     rax, [rsp+88h+var_28]
0x140001b6a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x140001b6f  lea     rax, ContextRecord
0x140001b76  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x140001b7b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x140001b80  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x140001b85  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x140001b8a  xor     ecx, ecx; HandlerType
0x140001b8c  call    cs:__imp_RtlVirtualUnwind
0x140001b92  nop
0x140001b93  jmp     short loc_140001BB8
0x140001b95  mov     rax, cs:ContextRecord.Rsp
0x140001b9c  mov     rax, [rax]
0x140001b9f  mov     cs:ContextRecord.Rip, rax
0x140001ba6  mov     rax, cs:ContextRecord.Rsp
0x140001bad  add     rax, 8
0x140001bb1  mov     cs:ContextRecord.Rsp, rax
0x140001bb8  mov     rax, cs:ContextRecord.Rip
0x140001bbf  mov     cs:qword_14000E370, rax
0x140001bc6  mov     rax, [rsp+88h+arg_0]
0x140001bce  mov     cs:ContextRecord.Rcx, rax
0x140001bd5  mov     cs:dword_14000E360, 0C0000409h
0x140001bdf  mov     cs:dword_14000E364, 1
0x140001be9  mov     cs:dword_14000E378, 3
0x140001bf3  mov     eax, 8
0x140001bf8  imul    rax, 0
0x140001bfc  lea     rcx, qword_14000E380
0x140001c03  mov     qword ptr [rcx+rax], 2
0x140001c0b  mov     eax, 8
0x140001c10  imul    rax, 1
0x140001c14  lea     rcx, qword_14000E380
0x140001c1b  mov     rdx, cs:__security_cookie
0x140001c22  mov     [rcx+rax], rdx
0x140001c26  mov     eax, 8
0x140001c2b  imul    rax, 2
0x140001c2f  lea     rcx, qword_14000E380
0x140001c36  mov     rdx, cs:__security_cookie_complement
0x140001c3d  mov     [rcx+rax], rdx
0x140001c41  mov     eax, 8
0x140001c46  imul    rax, 0
0x140001c4a  mov     rcx, cs:__security_cookie
0x140001c51  mov     [rsp+rax+88h+var_20], rcx
0x140001c56  mov     eax, 8
0x140001c5b  imul    rax, 1
0x140001c5f  mov     rcx, cs:__security_cookie_complement
0x140001c66  mov     [rsp+rax+88h+var_20], rcx
0x140001c6b  lea     rcx, ExceptionInfo; ExceptionInfo
0x140001c72  call    __raise_securityfailure
0x140001c77  nop
0x140001c78  add     rsp, 88h
0x140001c7f  retn
```
