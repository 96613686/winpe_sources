# __report_gsfailure

- ea: `0x1800018c0`
- end: `0x180001a60`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004ad0`

## callees

- `0x18000187c`
- `0x1800018c0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000191f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000191f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001900`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001900`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000196c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000196c`

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
  qword_1800090C0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_1800090B0 = -1073740791;
  dword_1800090B4 = 1;
  dword_1800090C8 = 3;
  qword_1800090D0[0] = 2;
  qword_1800090D0[1] = _security_cookie;
  qword_1800090D0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800018c0  mov     [rsp+arg_0], rcx
0x1800018c5  sub     rsp, 88h
0x1800018cc  mov     [rsp+88h+ControlPc], 0
0x1800018d5  mov     [rsp+88h+var_30], 0
0x1800018de  mov     [rsp+88h+FunctionEntry], 0
0x1800018e7  mov     [rsp+88h+var_28], 0
0x1800018f0  mov     [rsp+88h+ImageBase], 0
0x1800018f9  lea     rcx, ContextRecord; ContextRecord
0x180001900  call    cs:__imp_RtlCaptureContext
0x180001906  mov     rax, cs:ContextRecord.Rip
0x18000190d  mov     [rsp+88h+ControlPc], rax
0x180001912  xor     r8d, r8d; HistoryTable
0x180001915  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000191a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000191f  call    cs:__imp_RtlLookupFunctionEntry
0x180001925  mov     [rsp+88h+FunctionEntry], rax
0x18000192a  cmp     [rsp+88h+FunctionEntry], 0
0x180001930  jz      short loc_180001975
0x180001932  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000193b  lea     rax, [rsp+88h+var_30]
0x180001940  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001945  lea     rax, [rsp+88h+var_28]
0x18000194a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000194f  lea     rax, ContextRecord
0x180001956  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000195b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001960  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001965  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000196a  xor     ecx, ecx; HandlerType
0x18000196c  call    cs:__imp_RtlVirtualUnwind
0x180001972  nop
0x180001973  jmp     short loc_180001998
0x180001975  mov     rax, cs:ContextRecord.Rsp
0x18000197c  mov     rax, [rax]
0x18000197f  mov     cs:ContextRecord.Rip, rax
0x180001986  mov     rax, cs:ContextRecord.Rsp
0x18000198d  add     rax, 8
0x180001991  mov     cs:ContextRecord.Rsp, rax
0x180001998  mov     rax, cs:ContextRecord.Rip
0x18000199f  mov     cs:qword_1800090C0, rax
0x1800019a6  mov     rax, [rsp+88h+arg_0]
0x1800019ae  mov     cs:ContextRecord.Rcx, rax
0x1800019b5  mov     cs:dword_1800090B0, 0C0000409h
0x1800019bf  mov     cs:dword_1800090B4, 1
0x1800019c9  mov     cs:dword_1800090C8, 3
0x1800019d3  mov     eax, 8
0x1800019d8  imul    rax, 0
0x1800019dc  lea     rcx, qword_1800090D0
0x1800019e3  mov     qword ptr [rcx+rax], 2
0x1800019eb  mov     eax, 8
0x1800019f0  imul    rax, 1
0x1800019f4  lea     rcx, qword_1800090D0
0x1800019fb  mov     rdx, cs:__security_cookie
0x180001a02  mov     [rcx+rax], rdx
0x180001a06  mov     eax, 8
0x180001a0b  imul    rax, 2
0x180001a0f  lea     rcx, qword_1800090D0
0x180001a16  mov     rdx, cs:__security_cookie_complement
0x180001a1d  mov     [rcx+rax], rdx
0x180001a21  mov     eax, 8
0x180001a26  imul    rax, 0
0x180001a2a  mov     rcx, cs:__security_cookie
0x180001a31  mov     [rsp+rax+88h+var_20], rcx
0x180001a36  mov     eax, 8
0x180001a3b  imul    rax, 1
0x180001a3f  mov     rcx, cs:__security_cookie_complement
0x180001a46  mov     [rsp+rax+88h+var_20], rcx
0x180001a4b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001a52  call    __raise_securityfailure
0x180001a57  nop
0x180001a58  add     rsp, 88h
0x180001a5f  retn
```
