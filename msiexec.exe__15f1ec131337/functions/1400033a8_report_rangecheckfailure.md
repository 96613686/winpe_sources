# __report_rangecheckfailure

- ea: `0x1400033a8`
- end: `0x1400034ce`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: `void __noreturn()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400049a4`
- `0x140005084`

## callees

- `0x1400031b8`
- `0x1400033a8`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x1400033e0`
- `ntdll!RtlCaptureContext` at `0x1400033e0`
- `ntdll!RtlLookupFunctionEntry` at `0x1400033ff`
- `ntdll!RtlLookupFunctionEntry` at `0x1400033ff`
- `ntdll!RtlVirtualUnwind` at `0x14000344c`
- `ntdll!RtlVirtualUnwind` at `0x14000344c`

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
  qword_140010200 = ContextRecord.Rip;
  dword_1400101F0 = -1073740791;
  dword_1400101F4 = 1;
  dword_140010208 = 1;
  qword_140010210[0] = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1400033a8  sub     rsp, 78h
0x1400033ac  mov     [rsp+78h+ControlPc], 0
0x1400033b5  mov     [rsp+78h+var_20], 0
0x1400033be  mov     [rsp+78h+FunctionEntry], 0
0x1400033c7  mov     [rsp+78h+var_18], 0
0x1400033d0  mov     [rsp+78h+ImageBase], 0
0x1400033d9  lea     rcx, ContextRecord; ContextRecord
0x1400033e0  call    cs:__imp_RtlCaptureContext
0x1400033e6  mov     rax, cs:ContextRecord.Rip
0x1400033ed  mov     [rsp+78h+ControlPc], rax
0x1400033f2  xor     r8d, r8d; HistoryTable
0x1400033f5  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x1400033fa  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x1400033ff  call    cs:__imp_RtlLookupFunctionEntry
0x140003405  mov     [rsp+78h+FunctionEntry], rax
0x14000340a  cmp     [rsp+78h+FunctionEntry], 0
0x140003410  jz      short loc_140003455
0x140003412  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x14000341b  lea     rax, [rsp+78h+var_20]
0x140003420  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x140003425  lea     rax, [rsp+78h+var_18]
0x14000342a  mov     [rsp+78h+HandlerData], rax; HandlerData
0x14000342f  lea     rax, ContextRecord
0x140003436  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x14000343b  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x140003440  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x140003445  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x14000344a  xor     ecx, ecx; HandlerType
0x14000344c  call    cs:__imp_RtlVirtualUnwind
0x140003452  nop
0x140003453  jmp     short loc_140003478
0x140003455  mov     rax, cs:ContextRecord.Rsp
0x14000345c  mov     rax, [rax]
0x14000345f  mov     cs:ContextRecord.Rip, rax
0x140003466  mov     rax, cs:ContextRecord.Rsp
0x14000346d  add     rax, 8
0x140003471  mov     cs:ContextRecord.Rsp, rax
0x140003478  mov     rax, cs:ContextRecord.Rip
0x14000347f  mov     cs:qword_140010200, rax
0x140003486  mov     cs:dword_1400101F0, 0C0000409h
0x140003490  mov     cs:dword_1400101F4, 1
0x14000349a  mov     cs:dword_140010208, 1
0x1400034a4  mov     eax, 8
0x1400034a9  imul    rax, 0
0x1400034ad  lea     rcx, qword_140010210
0x1400034b4  mov     qword ptr [rcx+rax], 8
0x1400034bc  lea     rcx, ExceptionInfo; ExceptionInfo
0x1400034c3  call    __raise_securityfailure
0x1400034c8  nop
0x1400034c9  add     rsp, 78h
0x1400034cd  retn
```
