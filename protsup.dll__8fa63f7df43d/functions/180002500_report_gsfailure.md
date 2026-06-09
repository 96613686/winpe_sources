# __report_gsfailure

- ea: `0x180002500`
- end: `0x1800026a0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002760`

## callees

- `0x1800024bc`
- `0x180002500`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180002540`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180002540`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x1800025ac`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x1800025ac`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000255f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000255f`

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
0x180002500  mov     [rsp+arg_0], rcx
0x180002505  sub     rsp, 88h
0x18000250c  mov     [rsp+88h+ControlPc], 0
0x180002515  mov     [rsp+88h+var_30], 0
0x18000251e  mov     [rsp+88h+FunctionEntry], 0
0x180002527  mov     [rsp+88h+var_28], 0
0x180002530  mov     [rsp+88h+ImageBase], 0
0x180002539  lea     rcx, ContextRecord; ContextRecord
0x180002540  call    cs:__imp_RtlCaptureContext
0x180002546  mov     rax, cs:ContextRecord.Rip
0x18000254d  mov     [rsp+88h+ControlPc], rax
0x180002552  xor     r8d, r8d; HistoryTable
0x180002555  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000255a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000255f  call    cs:__imp_RtlLookupFunctionEntry
0x180002565  mov     [rsp+88h+FunctionEntry], rax
0x18000256a  cmp     [rsp+88h+FunctionEntry], 0
0x180002570  jz      short loc_1800025B5
0x180002572  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000257b  lea     rax, [rsp+88h+var_30]
0x180002580  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180002585  lea     rax, [rsp+88h+var_28]
0x18000258a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000258f  lea     rax, ContextRecord
0x180002596  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000259b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1800025a0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1800025a5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800025aa  xor     ecx, ecx; HandlerType
0x1800025ac  call    cs:__imp_RtlVirtualUnwind
0x1800025b2  nop
0x1800025b3  jmp     short loc_1800025D8
0x1800025b5  mov     rax, cs:ContextRecord.Rsp
0x1800025bc  mov     rax, [rax]
0x1800025bf  mov     cs:ContextRecord.Rip, rax
0x1800025c6  mov     rax, cs:ContextRecord.Rsp
0x1800025cd  add     rax, 8
0x1800025d1  mov     cs:ContextRecord.Rsp, rax
0x1800025d8  mov     rax, cs:ContextRecord.Rip
0x1800025df  mov     cs:qword_1800090C0, rax
0x1800025e6  mov     rax, [rsp+88h+arg_0]
0x1800025ee  mov     cs:ContextRecord.Rcx, rax
0x1800025f5  mov     cs:dword_1800090B0, 0C0000409h
0x1800025ff  mov     cs:dword_1800090B4, 1
0x180002609  mov     cs:dword_1800090C8, 3
0x180002613  mov     eax, 8
0x180002618  imul    rax, 0
0x18000261c  lea     rcx, qword_1800090D0
0x180002623  mov     qword ptr [rcx+rax], 2
0x18000262b  mov     eax, 8
0x180002630  imul    rax, 1
0x180002634  lea     rcx, qword_1800090D0
0x18000263b  mov     rdx, cs:__security_cookie
0x180002642  mov     [rcx+rax], rdx
0x180002646  mov     eax, 8
0x18000264b  imul    rax, 2
0x18000264f  lea     rcx, qword_1800090D0
0x180002656  mov     rdx, cs:__security_cookie_complement
0x18000265d  mov     [rcx+rax], rdx
0x180002661  mov     eax, 8
0x180002666  imul    rax, 0
0x18000266a  mov     rcx, cs:__security_cookie
0x180002671  mov     [rsp+rax+88h+var_20], rcx
0x180002676  mov     eax, 8
0x18000267b  imul    rax, 1
0x18000267f  mov     rcx, cs:__security_cookie_complement
0x180002686  mov     [rsp+rax+88h+var_20], rcx
0x18000268b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180002692  call    __raise_securityfailure
0x180002697  nop
0x180002698  add     rsp, 88h
0x18000269f  retn
```
