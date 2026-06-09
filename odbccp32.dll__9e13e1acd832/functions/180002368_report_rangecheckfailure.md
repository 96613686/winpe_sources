# __report_rangecheckfailure

- ea: `0x180002368`
- end: `0x18000248e`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: `void __noreturn()`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000295c`
- `0x1800069d8`
- `0x18000cfc4`
- `0x180014394`
- `0x18001484c`

## callees

- `0x180002178`
- `0x180002368`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x1800023a0`
- `ntdll!RtlCaptureContext` at `0x1800023a0`
- `ntdll!RtlLookupFunctionEntry` at `0x1800023bf`
- `ntdll!RtlLookupFunctionEntry` at `0x1800023bf`
- `ntdll!RtlVirtualUnwind` at `0x18000240c`
- `ntdll!RtlVirtualUnwind` at `0x18000240c`

## pseudocode

```c
void __noreturn _report_rangecheckfailure()
{
  struct _RUNTIME_FUNCTION *FunctionEntry; // [rsp+40h] [rbp-38h]
  DWORD64 ControlPc; // [rsp+48h] [rbp-30h]
  unsigned __int64 ImageBase; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+58h] [rbp-20h] BYREF
  PVOID HandlerData; // [rsp+60h] [rbp-18h] BYREF

  EstablisherFrame = 0;
  HandlerData = 0;
  ImageBase = 0;
  RtlCaptureContext(&ContextRecord);
  ControlPc = ContextRecord.Rip;
  FunctionEntry = RtlLookupFunctionEntry(ContextRecord.Rip, &ImageBase, 0);
  if ( FunctionEntry )
  {
    RtlVirtualUnwind(0, ImageBase, ControlPc, FunctionEntry, &ContextRecord, &HandlerData, &EstablisherFrame, 0);
  }
  else
  {
    ContextRecord.Rip = *(_QWORD *)ContextRecord.Rsp;
    ContextRecord.Rsp += 8LL;
  }
  qword_18001C200 = ContextRecord.Rip;
  dword_18001C1F0 = -1073740791;
  dword_18001C1F4 = 1;
  dword_18001C208 = 1;
  qword_18001C210[0] = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180002368  sub     rsp, 78h
0x18000236c  mov     [rsp+78h+ControlPc], 0
0x180002375  mov     [rsp+78h+var_20], 0
0x18000237e  mov     [rsp+78h+FunctionEntry], 0
0x180002387  mov     [rsp+78h+var_18], 0
0x180002390  mov     [rsp+78h+ImageBase], 0
0x180002399  lea     rcx, ContextRecord; ContextRecord
0x1800023a0  call    cs:__imp_RtlCaptureContext
0x1800023a6  mov     rax, cs:ContextRecord.Rip
0x1800023ad  mov     [rsp+78h+ControlPc], rax
0x1800023b2  xor     r8d, r8d; HistoryTable
0x1800023b5  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x1800023ba  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x1800023bf  call    cs:__imp_RtlLookupFunctionEntry
0x1800023c5  mov     [rsp+78h+FunctionEntry], rax
0x1800023ca  cmp     [rsp+78h+FunctionEntry], 0
0x1800023d0  jz      short loc_180002415
0x1800023d2  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x1800023db  lea     rax, [rsp+78h+var_20]
0x1800023e0  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x1800023e5  lea     rax, [rsp+78h+var_18]
0x1800023ea  mov     [rsp+78h+HandlerData], rax; HandlerData
0x1800023ef  lea     rax, ContextRecord
0x1800023f6  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x1800023fb  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x180002400  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x180002405  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000240a  xor     ecx, ecx; HandlerType
0x18000240c  call    cs:__imp_RtlVirtualUnwind
0x180002412  nop
0x180002413  jmp     short loc_180002438
0x180002415  mov     rax, cs:ContextRecord.Rsp
0x18000241c  mov     rax, [rax]
0x18000241f  mov     cs:ContextRecord.Rip, rax
0x180002426  mov     rax, cs:ContextRecord.Rsp
0x18000242d  add     rax, 8
0x180002431  mov     cs:ContextRecord.Rsp, rax
0x180002438  mov     rax, cs:ContextRecord.Rip
0x18000243f  mov     cs:qword_18001C200, rax
0x180002446  mov     cs:dword_18001C1F0, 0C0000409h
0x180002450  mov     cs:dword_18001C1F4, 1
0x18000245a  mov     cs:dword_18001C208, 1
0x180002464  mov     eax, 8
0x180002469  imul    rax, 0
0x18000246d  lea     rcx, qword_18001C210
0x180002474  mov     qword ptr [rcx+rax], 8
0x18000247c  lea     rcx, ExceptionInfo; ExceptionInfo
0x180002483  call    __raise_securityfailure
0x180002488  nop
0x180002489  add     rsp, 78h
0x18000248d  retn
```
