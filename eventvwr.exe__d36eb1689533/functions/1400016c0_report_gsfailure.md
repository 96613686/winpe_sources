# __report_gsfailure

- ea: `0x1400016c0`
- end: `0x140001860`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002cb0`

## callees

- `0x140001680`
- `0x1400016c0`

## import_xrefs

- `KERNEL32!RtlVirtualUnwind` at `0x14000176c`
- `KERNEL32!RtlVirtualUnwind` at `0x14000176c`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000171f`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000171f`
- `KERNEL32!RtlCaptureContext` at `0x140001700`
- `KERNEL32!RtlCaptureContext` at `0x140001700`

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
  qword_1400060F0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_1400060E0 = -1073740791;
  dword_1400060E4 = 1;
  dword_1400060F8 = 3;
  qword_140006100[0] = 2;
  qword_140006100[1] = _security_cookie;
  qword_140006100[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1400016c0  mov     [rsp+arg_0], rcx
0x1400016c5  sub     rsp, 88h
0x1400016cc  mov     [rsp+88h+ControlPc], 0
0x1400016d5  mov     [rsp+88h+var_30], 0
0x1400016de  mov     [rsp+88h+FunctionEntry], 0
0x1400016e7  mov     [rsp+88h+var_28], 0
0x1400016f0  mov     [rsp+88h+ImageBase], 0
0x1400016f9  lea     rcx, ContextRecord; ContextRecord
0x140001700  call    cs:__imp_RtlCaptureContext
0x140001706  mov     rax, cs:ContextRecord.Rip
0x14000170d  mov     [rsp+88h+ControlPc], rax
0x140001712  xor     r8d, r8d; HistoryTable
0x140001715  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x14000171a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x14000171f  call    cs:__imp_RtlLookupFunctionEntry
0x140001725  mov     [rsp+88h+FunctionEntry], rax
0x14000172a  cmp     [rsp+88h+FunctionEntry], 0
0x140001730  jz      short loc_140001775
0x140001732  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x14000173b  lea     rax, [rsp+88h+var_30]
0x140001740  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x140001745  lea     rax, [rsp+88h+var_28]
0x14000174a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x14000174f  lea     rax, ContextRecord
0x140001756  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x14000175b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x140001760  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x140001765  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x14000176a  xor     ecx, ecx; HandlerType
0x14000176c  call    cs:__imp_RtlVirtualUnwind
0x140001772  nop
0x140001773  jmp     short loc_140001798
0x140001775  mov     rax, cs:ContextRecord.Rsp
0x14000177c  mov     rax, [rax]
0x14000177f  mov     cs:ContextRecord.Rip, rax
0x140001786  mov     rax, cs:ContextRecord.Rsp
0x14000178d  add     rax, 8
0x140001791  mov     cs:ContextRecord.Rsp, rax
0x140001798  mov     rax, cs:ContextRecord.Rip
0x14000179f  mov     cs:qword_1400060F0, rax
0x1400017a6  mov     rax, [rsp+88h+arg_0]
0x1400017ae  mov     cs:ContextRecord.Rcx, rax
0x1400017b5  mov     cs:dword_1400060E0, 0C0000409h
0x1400017bf  mov     cs:dword_1400060E4, 1
0x1400017c9  mov     cs:dword_1400060F8, 3
0x1400017d3  mov     eax, 8
0x1400017d8  imul    rax, 0
0x1400017dc  lea     rcx, qword_140006100
0x1400017e3  mov     qword ptr [rcx+rax], 2
0x1400017eb  mov     eax, 8
0x1400017f0  imul    rax, 1
0x1400017f4  lea     rcx, qword_140006100
0x1400017fb  mov     rdx, cs:__security_cookie
0x140001802  mov     [rcx+rax], rdx
0x140001806  mov     eax, 8
0x14000180b  imul    rax, 2
0x14000180f  lea     rcx, qword_140006100
0x140001816  mov     rdx, cs:__security_cookie_complement
0x14000181d  mov     [rcx+rax], rdx
0x140001821  mov     eax, 8
0x140001826  imul    rax, 0
0x14000182a  mov     rcx, cs:__security_cookie
0x140001831  mov     [rsp+rax+88h+var_20], rcx
0x140001836  mov     eax, 8
0x14000183b  imul    rax, 1
0x14000183f  mov     rcx, cs:__security_cookie_complement
0x140001846  mov     [rsp+rax+88h+var_20], rcx
0x14000184b  lea     rcx, ExceptionInfo; ExceptionInfo
0x140001852  call    __raise_securityfailure
0x140001857  nop
0x140001858  add     rsp, 88h
0x14000185f  retn
```
