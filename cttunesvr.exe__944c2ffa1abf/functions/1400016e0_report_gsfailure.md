# __report_gsfailure

- ea: `0x1400016e0`
- end: `0x140001880`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400065f0`

## callees

- `0x14000169c`
- `0x1400016e0`

## import_xrefs

- `KERNEL32!RtlVirtualUnwind` at `0x14000178c`
- `KERNEL32!RtlVirtualUnwind` at `0x14000178c`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000173f`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000173f`
- `KERNEL32!RtlCaptureContext` at `0x140001720`
- `KERNEL32!RtlCaptureContext` at `0x140001720`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *FunctionEntry; // [rsp+40h] [rbp-48h]
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
  qword_14000B260 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_14000B250 = -1073740791;
  dword_14000B254 = 1;
  dword_14000B268 = 3;
  qword_14000B270[0] = 2;
  qword_14000B270[1] = _security_cookie;
  qword_14000B270[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1400016e0  mov     [rsp+arg_0], rcx
0x1400016e5  sub     rsp, 88h
0x1400016ec  mov     [rsp+88h+ControlPc], 0
0x1400016f5  mov     [rsp+88h+var_30], 0
0x1400016fe  mov     [rsp+88h+FunctionEntry], 0
0x140001707  mov     [rsp+88h+var_28], 0
0x140001710  mov     [rsp+88h+ImageBase], 0
0x140001719  lea     rcx, ContextRecord; ContextRecord
0x140001720  call    cs:__imp_RtlCaptureContext
0x140001726  mov     rax, cs:ContextRecord.Rip
0x14000172d  mov     [rsp+88h+ControlPc], rax
0x140001732  xor     r8d, r8d; HistoryTable
0x140001735  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x14000173a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x14000173f  call    cs:__imp_RtlLookupFunctionEntry
0x140001745  mov     [rsp+88h+FunctionEntry], rax
0x14000174a  cmp     [rsp+88h+FunctionEntry], 0
0x140001750  jz      short loc_140001795
0x140001752  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x14000175b  lea     rax, [rsp+88h+var_30]
0x140001760  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x140001765  lea     rax, [rsp+88h+var_28]
0x14000176a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x14000176f  lea     rax, ContextRecord
0x140001776  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x14000177b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x140001780  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x140001785  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x14000178a  xor     ecx, ecx; HandlerType
0x14000178c  call    cs:__imp_RtlVirtualUnwind
0x140001792  nop
0x140001793  jmp     short loc_1400017B8
0x140001795  mov     rax, cs:ContextRecord.Rsp
0x14000179c  mov     rax, [rax]
0x14000179f  mov     cs:ContextRecord.Rip, rax
0x1400017a6  mov     rax, cs:ContextRecord.Rsp
0x1400017ad  add     rax, 8
0x1400017b1  mov     cs:ContextRecord.Rsp, rax
0x1400017b8  mov     rax, cs:ContextRecord.Rip
0x1400017bf  mov     cs:qword_14000B260, rax
0x1400017c6  mov     rax, [rsp+88h+arg_0]
0x1400017ce  mov     cs:ContextRecord.Rcx, rax
0x1400017d5  mov     cs:dword_14000B250, 0C0000409h
0x1400017df  mov     cs:dword_14000B254, 1
0x1400017e9  mov     cs:dword_14000B268, 3
0x1400017f3  mov     eax, 8
0x1400017f8  imul    rax, 0
0x1400017fc  lea     rcx, qword_14000B270
0x140001803  mov     qword ptr [rcx+rax], 2
0x14000180b  mov     eax, 8
0x140001810  imul    rax, 1
0x140001814  lea     rcx, qword_14000B270
0x14000181b  mov     rdx, cs:__security_cookie
0x140001822  mov     [rcx+rax], rdx
0x140001826  mov     eax, 8
0x14000182b  imul    rax, 2
0x14000182f  lea     rcx, qword_14000B270
0x140001836  mov     rdx, cs:__security_cookie_complement
0x14000183d  mov     [rcx+rax], rdx
0x140001841  mov     eax, 8
0x140001846  imul    rax, 0
0x14000184a  mov     rcx, cs:__security_cookie
0x140001851  mov     [rsp+rax+88h+var_20], rcx
0x140001856  mov     eax, 8
0x14000185b  imul    rax, 1
0x14000185f  mov     rcx, cs:__security_cookie_complement
0x140001866  mov     [rsp+rax+88h+var_20], rcx
0x14000186b  lea     rcx, ExceptionInfo; ExceptionInfo
0x140001872  call    __raise_securityfailure
0x140001877  nop
0x140001878  add     rsp, 88h
0x14000187f  retn
```
