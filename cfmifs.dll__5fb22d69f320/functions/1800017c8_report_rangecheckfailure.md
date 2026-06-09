# __report_rangecheckfailure

- ea: `0x1800017c8`
- end: `0x1800018ee`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000547c`
- `0x18000579c`

## callees

- `0x1800015e4`
- `0x1800017c8`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000181f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000181f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000186c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000186c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001800`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001800`

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
  qword_18000B240 = ContextRecord.Rip;
  dword_18000B230 = -1073740791;
  dword_18000B234 = 1;
  dword_18000B248 = 1;
  qword_18000B250[0] = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800017c8  sub     rsp, 78h
0x1800017cc  mov     [rsp+78h+ControlPc], 0
0x1800017d5  mov     [rsp+78h+var_20], 0
0x1800017de  mov     [rsp+78h+FunctionEntry], 0
0x1800017e7  mov     [rsp+78h+var_18], 0
0x1800017f0  mov     [rsp+78h+ImageBase], 0
0x1800017f9  lea     rcx, ContextRecord; ContextRecord
0x180001800  call    cs:__imp_RtlCaptureContext
0x180001806  mov     rax, cs:ContextRecord.Rip
0x18000180d  mov     [rsp+78h+ControlPc], rax
0x180001812  xor     r8d, r8d; HistoryTable
0x180001815  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000181a  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x18000181f  call    cs:__imp_RtlLookupFunctionEntry
0x180001825  mov     [rsp+78h+FunctionEntry], rax
0x18000182a  cmp     [rsp+78h+FunctionEntry], 0
0x180001830  jz      short loc_180001875
0x180001832  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x18000183b  lea     rax, [rsp+78h+var_20]
0x180001840  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x180001845  lea     rax, [rsp+78h+var_18]
0x18000184a  mov     [rsp+78h+HandlerData], rax; HandlerData
0x18000184f  lea     rax, ContextRecord
0x180001856  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x18000185b  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x180001860  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x180001865  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000186a  xor     ecx, ecx; HandlerType
0x18000186c  call    cs:__imp_RtlVirtualUnwind
0x180001872  nop
0x180001873  jmp     short loc_180001898
0x180001875  mov     rax, cs:ContextRecord.Rsp
0x18000187c  mov     rax, [rax]
0x18000187f  mov     cs:ContextRecord.Rip, rax
0x180001886  mov     rax, cs:ContextRecord.Rsp
0x18000188d  add     rax, 8
0x180001891  mov     cs:ContextRecord.Rsp, rax
0x180001898  mov     rax, cs:ContextRecord.Rip
0x18000189f  mov     cs:qword_18000B240, rax
0x1800018a6  mov     cs:dword_18000B230, 0C0000409h
0x1800018b0  mov     cs:dword_18000B234, 1
0x1800018ba  mov     cs:dword_18000B248, 1
0x1800018c4  mov     eax, 8
0x1800018c9  imul    rax, 0
0x1800018cd  lea     rcx, qword_18000B250
0x1800018d4  mov     qword ptr [rcx+rax], 8
0x1800018dc  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800018e3  call    __raise_securityfailure
0x1800018e8  nop
0x1800018e9  add     rsp, 78h
0x1800018ed  retn
```
