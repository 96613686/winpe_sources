# __report_rangecheckfailure

- ea: `0x140001508`
- end: `0x14000162e`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003a30`
- `0x14000907c`
- `0x140009454`
- `0x14000cb80`
- `0x14000cec0`
- `0x14000d9c8`

## callees

- `0x140001318`
- `0x140001508`

## import_xrefs

- `KERNEL32!RtlVirtualUnwind` at `0x1400015ac`
- `KERNEL32!RtlVirtualUnwind` at `0x1400015ac`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000155f`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000155f`
- `KERNEL32!RtlCaptureContext` at `0x140001540`
- `KERNEL32!RtlCaptureContext` at `0x140001540`

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
  qword_1400161E0 = ContextRecord.Rip;
  dword_1400161D0 = -1073740791;
  dword_1400161D4 = 1;
  dword_1400161E8 = 1;
  qword_1400161F0[0] = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x140001508  sub     rsp, 78h
0x14000150c  mov     [rsp+78h+ControlPc], 0
0x140001515  mov     [rsp+78h+var_20], 0
0x14000151e  mov     [rsp+78h+FunctionEntry], 0
0x140001527  mov     [rsp+78h+var_18], 0
0x140001530  mov     [rsp+78h+ImageBase], 0
0x140001539  lea     rcx, ContextRecord; ContextRecord
0x140001540  call    cs:__imp_RtlCaptureContext
0x140001546  mov     rax, cs:ContextRecord.Rip
0x14000154d  mov     [rsp+78h+ControlPc], rax
0x140001552  xor     r8d, r8d; HistoryTable
0x140001555  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x14000155a  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x14000155f  call    cs:__imp_RtlLookupFunctionEntry
0x140001565  mov     [rsp+78h+FunctionEntry], rax
0x14000156a  cmp     [rsp+78h+FunctionEntry], 0
0x140001570  jz      short loc_1400015B5
0x140001572  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x14000157b  lea     rax, [rsp+78h+var_20]
0x140001580  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x140001585  lea     rax, [rsp+78h+var_18]
0x14000158a  mov     [rsp+78h+HandlerData], rax; HandlerData
0x14000158f  lea     rax, ContextRecord
0x140001596  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x14000159b  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x1400015a0  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x1400015a5  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x1400015aa  xor     ecx, ecx; HandlerType
0x1400015ac  call    cs:__imp_RtlVirtualUnwind
0x1400015b2  nop
0x1400015b3  jmp     short loc_1400015D8
0x1400015b5  mov     rax, cs:ContextRecord.Rsp
0x1400015bc  mov     rax, [rax]
0x1400015bf  mov     cs:ContextRecord.Rip, rax
0x1400015c6  mov     rax, cs:ContextRecord.Rsp
0x1400015cd  add     rax, 8
0x1400015d1  mov     cs:ContextRecord.Rsp, rax
0x1400015d8  mov     rax, cs:ContextRecord.Rip
0x1400015df  mov     cs:qword_1400161E0, rax
0x1400015e6  mov     cs:dword_1400161D0, 0C0000409h
0x1400015f0  mov     cs:dword_1400161D4, 1
0x1400015fa  mov     cs:dword_1400161E8, 1
0x140001604  mov     eax, 8
0x140001609  imul    rax, 0
0x14000160d  lea     rcx, qword_1400161F0
0x140001614  mov     qword ptr [rcx+rax], 8
0x14000161c  lea     rcx, ExceptionInfo; ExceptionInfo
0x140001623  call    __raise_securityfailure
0x140001628  nop
0x140001629  add     rsp, 78h
0x14000162d  retn
```
