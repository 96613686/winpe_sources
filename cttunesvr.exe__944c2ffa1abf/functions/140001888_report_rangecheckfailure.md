# __report_rangecheckfailure

- ea: `0x140001888`
- end: `0x1400019ae`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004f48`
- `0x1400059e8`

## callees

- `0x14000169c`
- `0x140001888`

## import_xrefs

- `KERNEL32!RtlVirtualUnwind` at `0x14000192c`
- `KERNEL32!RtlVirtualUnwind` at `0x14000192c`
- `KERNEL32!RtlLookupFunctionEntry` at `0x1400018df`
- `KERNEL32!RtlLookupFunctionEntry` at `0x1400018df`
- `KERNEL32!RtlCaptureContext` at `0x1400018c0`
- `KERNEL32!RtlCaptureContext` at `0x1400018c0`

## pseudocode

```c
void __noreturn _report_rangecheckfailure()
{
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *FunctionEntry; // [rsp+40h] [rbp-38h]
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
  qword_14000B260 = ContextRecord.Rip;
  dword_14000B250 = -1073740791;
  dword_14000B254 = 1;
  dword_14000B268 = 1;
  qword_14000B270[0] = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x140001888  sub     rsp, 78h
0x14000188c  mov     [rsp+78h+ControlPc], 0
0x140001895  mov     [rsp+78h+var_20], 0
0x14000189e  mov     [rsp+78h+FunctionEntry], 0
0x1400018a7  mov     [rsp+78h+var_18], 0
0x1400018b0  mov     [rsp+78h+ImageBase], 0
0x1400018b9  lea     rcx, ContextRecord; ContextRecord
0x1400018c0  call    cs:__imp_RtlCaptureContext
0x1400018c6  mov     rax, cs:ContextRecord.Rip
0x1400018cd  mov     [rsp+78h+ControlPc], rax
0x1400018d2  xor     r8d, r8d; HistoryTable
0x1400018d5  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x1400018da  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x1400018df  call    cs:__imp_RtlLookupFunctionEntry
0x1400018e5  mov     [rsp+78h+FunctionEntry], rax
0x1400018ea  cmp     [rsp+78h+FunctionEntry], 0
0x1400018f0  jz      short loc_140001935
0x1400018f2  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x1400018fb  lea     rax, [rsp+78h+var_20]
0x140001900  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x140001905  lea     rax, [rsp+78h+var_18]
0x14000190a  mov     [rsp+78h+HandlerData], rax; HandlerData
0x14000190f  lea     rax, ContextRecord
0x140001916  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x14000191b  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x140001920  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x140001925  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x14000192a  xor     ecx, ecx; HandlerType
0x14000192c  call    cs:__imp_RtlVirtualUnwind
0x140001932  nop
0x140001933  jmp     short loc_140001958
0x140001935  mov     rax, cs:ContextRecord.Rsp
0x14000193c  mov     rax, [rax]
0x14000193f  mov     cs:ContextRecord.Rip, rax
0x140001946  mov     rax, cs:ContextRecord.Rsp
0x14000194d  add     rax, 8
0x140001951  mov     cs:ContextRecord.Rsp, rax
0x140001958  mov     rax, cs:ContextRecord.Rip
0x14000195f  mov     cs:qword_14000B260, rax
0x140001966  mov     cs:dword_14000B250, 0C0000409h
0x140001970  mov     cs:dword_14000B254, 1
0x14000197a  mov     cs:dword_14000B268, 1
0x140001984  mov     eax, 8
0x140001989  imul    rax, 0
0x14000198d  lea     rcx, qword_14000B270
0x140001994  mov     qword ptr [rcx+rax], 8
0x14000199c  lea     rcx, ExceptionInfo; ExceptionInfo
0x1400019a3  call    __raise_securityfailure
0x1400019a8  nop
0x1400019a9  add     rsp, 78h
0x1400019ad  retn
```
