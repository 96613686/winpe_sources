# __report_rangecheckfailure

- ea: `0x180005688`
- end: `0x1800057ae`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004220`

## callees

- `0x180005498`
- `0x180005688`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000572c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000572c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800056c0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800056c0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1800056df`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1800056df`

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
  qword_18000A0C0 = ContextRecord.Rip;
  dword_18000A0B0 = -1073740791;
  dword_18000A0B4 = 1;
  dword_18000A0C8 = 1;
  qword_18000A0D0[0] = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180005688  sub     rsp, 78h
0x18000568c  mov     [rsp+78h+ControlPc], 0
0x180005695  mov     [rsp+78h+var_20], 0
0x18000569e  mov     [rsp+78h+FunctionEntry], 0
0x1800056a7  mov     [rsp+78h+var_18], 0
0x1800056b0  mov     [rsp+78h+ImageBase], 0
0x1800056b9  lea     rcx, ContextRecord; ContextRecord
0x1800056c0  call    cs:__imp_RtlCaptureContext
0x1800056c6  mov     rax, cs:ContextRecord.Rip
0x1800056cd  mov     [rsp+78h+ControlPc], rax
0x1800056d2  xor     r8d, r8d; HistoryTable
0x1800056d5  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x1800056da  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x1800056df  call    cs:__imp_RtlLookupFunctionEntry
0x1800056e5  mov     [rsp+78h+FunctionEntry], rax
0x1800056ea  cmp     [rsp+78h+FunctionEntry], 0
0x1800056f0  jz      short loc_180005735
0x1800056f2  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x1800056fb  lea     rax, [rsp+78h+var_20]
0x180005700  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x180005705  lea     rax, [rsp+78h+var_18]
0x18000570a  mov     [rsp+78h+HandlerData], rax; HandlerData
0x18000570f  lea     rax, ContextRecord
0x180005716  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x18000571b  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x180005720  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x180005725  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000572a  xor     ecx, ecx; HandlerType
0x18000572c  call    cs:__imp_RtlVirtualUnwind
0x180005732  nop
0x180005733  jmp     short loc_180005758
0x180005735  mov     rax, cs:ContextRecord.Rsp
0x18000573c  mov     rax, [rax]
0x18000573f  mov     cs:ContextRecord.Rip, rax
0x180005746  mov     rax, cs:ContextRecord.Rsp
0x18000574d  add     rax, 8
0x180005751  mov     cs:ContextRecord.Rsp, rax
0x180005758  mov     rax, cs:ContextRecord.Rip
0x18000575f  mov     cs:qword_18000A0C0, rax
0x180005766  mov     cs:dword_18000A0B0, 0C0000409h
0x180005770  mov     cs:dword_18000A0B4, 1
0x18000577a  mov     cs:dword_18000A0C8, 1
0x180005784  mov     eax, 8
0x180005789  imul    rax, 0
0x18000578d  lea     rcx, qword_18000A0D0
0x180005794  mov     qword ptr [rcx+rax], 8
0x18000579c  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800057a3  call    __raise_securityfailure
0x1800057a8  nop
0x1800057a9  add     rsp, 78h
0x1800057ad  retn
```
