# __report_rangecheckfailure

- ea: `0x1800016d8`
- end: `0x1800017fe`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004630`

## callees

- `0x1800014f0`
- `0x1800016d8`

## import_xrefs

- `KERNEL32!RtlCaptureContext` at `0x180001710`
- `KERNEL32!RtlCaptureContext` at `0x180001710`
- `KERNEL32!RtlLookupFunctionEntry` at `0x18000172f`
- `KERNEL32!RtlLookupFunctionEntry` at `0x18000172f`
- `KERNEL32!RtlVirtualUnwind` at `0x18000177c`
- `KERNEL32!RtlVirtualUnwind` at `0x18000177c`

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
  qword_18000C140 = ContextRecord.Rip;
  dword_18000C130 = -1073740791;
  dword_18000C134 = 1;
  dword_18000C148 = 1;
  qword_18000C150[0] = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800016d8  sub     rsp, 78h
0x1800016dc  mov     [rsp+78h+ControlPc], 0
0x1800016e5  mov     [rsp+78h+var_20], 0
0x1800016ee  mov     [rsp+78h+FunctionEntry], 0
0x1800016f7  mov     [rsp+78h+var_18], 0
0x180001700  mov     [rsp+78h+ImageBase], 0
0x180001709  lea     rcx, ContextRecord; ContextRecord
0x180001710  call    cs:__imp_RtlCaptureContext
0x180001716  mov     rax, cs:ContextRecord.Rip
0x18000171d  mov     [rsp+78h+ControlPc], rax
0x180001722  xor     r8d, r8d; HistoryTable
0x180001725  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000172a  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x18000172f  call    cs:__imp_RtlLookupFunctionEntry
0x180001735  mov     [rsp+78h+FunctionEntry], rax
0x18000173a  cmp     [rsp+78h+FunctionEntry], 0
0x180001740  jz      short loc_180001785
0x180001742  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x18000174b  lea     rax, [rsp+78h+var_20]
0x180001750  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x180001755  lea     rax, [rsp+78h+var_18]
0x18000175a  mov     [rsp+78h+HandlerData], rax; HandlerData
0x18000175f  lea     rax, ContextRecord
0x180001766  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x18000176b  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x180001770  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x180001775  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000177a  xor     ecx, ecx; HandlerType
0x18000177c  call    cs:__imp_RtlVirtualUnwind
0x180001782  nop
0x180001783  jmp     short loc_1800017A8
0x180001785  mov     rax, cs:ContextRecord.Rsp
0x18000178c  mov     rax, [rax]
0x18000178f  mov     cs:ContextRecord.Rip, rax
0x180001796  mov     rax, cs:ContextRecord.Rsp
0x18000179d  add     rax, 8
0x1800017a1  mov     cs:ContextRecord.Rsp, rax
0x1800017a8  mov     rax, cs:ContextRecord.Rip
0x1800017af  mov     cs:qword_18000C140, rax
0x1800017b6  mov     cs:dword_18000C130, 0C0000409h
0x1800017c0  mov     cs:dword_18000C134, 1
0x1800017ca  mov     cs:dword_18000C148, 1
0x1800017d4  mov     eax, 8
0x1800017d9  imul    rax, 0
0x1800017dd  lea     rcx, qword_18000C150
0x1800017e4  mov     qword ptr [rcx+rax], 8
0x1800017ec  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800017f3  call    __raise_securityfailure
0x1800017f8  nop
0x1800017f9  add     rsp, 78h
0x1800017fd  retn
```
