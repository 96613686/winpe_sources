# __report_gsfailure

- ea: `0x180001920`
- end: `0x180001ac0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004920`

## callees

- `0x1800018e4`
- `0x180001920`

## import_xrefs

- `KERNEL32!RtlLookupFunctionEntry` at `0x18000197f`
- `KERNEL32!RtlLookupFunctionEntry` at `0x18000197f`
- `KERNEL32!RtlCaptureContext` at `0x180001960`
- `KERNEL32!RtlCaptureContext` at `0x180001960`
- `KERNEL32!RtlVirtualUnwind` at `0x1800019cc`
- `KERNEL32!RtlVirtualUnwind` at `0x1800019cc`

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
  qword_1800091A0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_180009190 = -1073740791;
  dword_180009194 = 1;
  dword_1800091A8 = 3;
  qword_1800091B0[0] = 2;
  qword_1800091B0[1] = _security_cookie;
  qword_1800091B0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001920  mov     [rsp+arg_0], rcx
0x180001925  sub     rsp, 88h
0x18000192c  mov     [rsp+88h+ControlPc], 0
0x180001935  mov     [rsp+88h+var_30], 0
0x18000193e  mov     [rsp+88h+FunctionEntry], 0
0x180001947  mov     [rsp+88h+var_28], 0
0x180001950  mov     [rsp+88h+ImageBase], 0
0x180001959  lea     rcx, ContextRecord; ContextRecord
0x180001960  call    cs:__imp_RtlCaptureContext
0x180001966  mov     rax, cs:ContextRecord.Rip
0x18000196d  mov     [rsp+88h+ControlPc], rax
0x180001972  xor     r8d, r8d; HistoryTable
0x180001975  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000197a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000197f  call    cs:__imp_RtlLookupFunctionEntry
0x180001985  mov     [rsp+88h+FunctionEntry], rax
0x18000198a  cmp     [rsp+88h+FunctionEntry], 0
0x180001990  jz      short loc_1800019D5
0x180001992  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000199b  lea     rax, [rsp+88h+var_30]
0x1800019a0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1800019a5  lea     rax, [rsp+88h+var_28]
0x1800019aa  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1800019af  lea     rax, ContextRecord
0x1800019b6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1800019bb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1800019c0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1800019c5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800019ca  xor     ecx, ecx; HandlerType
0x1800019cc  call    cs:__imp_RtlVirtualUnwind
0x1800019d2  nop
0x1800019d3  jmp     short loc_1800019F8
0x1800019d5  mov     rax, cs:ContextRecord.Rsp
0x1800019dc  mov     rax, [rax]
0x1800019df  mov     cs:ContextRecord.Rip, rax
0x1800019e6  mov     rax, cs:ContextRecord.Rsp
0x1800019ed  add     rax, 8
0x1800019f1  mov     cs:ContextRecord.Rsp, rax
0x1800019f8  mov     rax, cs:ContextRecord.Rip
0x1800019ff  mov     cs:qword_1800091A0, rax
0x180001a06  mov     rax, [rsp+88h+arg_0]
0x180001a0e  mov     cs:ContextRecord.Rcx, rax
0x180001a15  mov     cs:dword_180009190, 0C0000409h
0x180001a1f  mov     cs:dword_180009194, 1
0x180001a29  mov     cs:dword_1800091A8, 3
0x180001a33  mov     eax, 8
0x180001a38  imul    rax, 0
0x180001a3c  lea     rcx, qword_1800091B0
0x180001a43  mov     qword ptr [rcx+rax], 2
0x180001a4b  mov     eax, 8
0x180001a50  imul    rax, 1
0x180001a54  lea     rcx, qword_1800091B0
0x180001a5b  mov     rdx, cs:__security_cookie
0x180001a62  mov     [rcx+rax], rdx
0x180001a66  mov     eax, 8
0x180001a6b  imul    rax, 2
0x180001a6f  lea     rcx, qword_1800091B0
0x180001a76  mov     rdx, cs:__security_cookie_complement
0x180001a7d  mov     [rcx+rax], rdx
0x180001a81  mov     eax, 8
0x180001a86  imul    rax, 0
0x180001a8a  mov     rcx, cs:__security_cookie
0x180001a91  mov     [rsp+rax+88h+var_20], rcx
0x180001a96  mov     eax, 8
0x180001a9b  imul    rax, 1
0x180001a9f  mov     rcx, cs:__security_cookie_complement
0x180001aa6  mov     [rsp+rax+88h+var_20], rcx
0x180001aab  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001ab2  call    __raise_securityfailure
0x180001ab7  nop
0x180001ab8  add     rsp, 88h
0x180001abf  retn
```
