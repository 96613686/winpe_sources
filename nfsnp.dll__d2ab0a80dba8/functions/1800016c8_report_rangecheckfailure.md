# __report_rangecheckfailure

- ea: `0x1800016c8`
- end: `0x1800017ee`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: `void __noreturn(void)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004720`
- `0x18000be24`
- `0x18000cc98`
- `0x18000eccc`
- `0x18000fc20`
- `0x180010310`
- `0x180010a40`

## callees

- `0x1800014d8`
- `0x1800016c8`

## import_xrefs

- `ntdll!RtlVirtualUnwind` at `0x18000176c`
- `ntdll!RtlVirtualUnwind` at `0x18000176c`
- `ntdll!RtlLookupFunctionEntry` at `0x18000171f`
- `ntdll!RtlLookupFunctionEntry` at `0x18000171f`
- `ntdll!RtlCaptureContext` at `0x180001700`
- `ntdll!RtlCaptureContext` at `0x180001700`

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
  qword_180018160 = ContextRecord.Rip;
  dword_180018150 = -1073740791;
  dword_180018154 = 1;
  dword_180018168 = 1;
  qword_180018170[0] = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800016c8  sub     rsp, 78h
0x1800016cc  mov     [rsp+78h+ControlPc], 0
0x1800016d5  mov     [rsp+78h+var_20], 0
0x1800016de  mov     [rsp+78h+FunctionEntry], 0
0x1800016e7  mov     [rsp+78h+var_18], 0
0x1800016f0  mov     [rsp+78h+ImageBase], 0
0x1800016f9  lea     rcx, ContextRecord; ContextRecord
0x180001700  call    cs:__imp_RtlCaptureContext
0x180001706  mov     rax, cs:ContextRecord.Rip
0x18000170d  mov     [rsp+78h+ControlPc], rax
0x180001712  xor     r8d, r8d; HistoryTable
0x180001715  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000171a  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x18000171f  call    cs:__imp_RtlLookupFunctionEntry
0x180001725  mov     [rsp+78h+FunctionEntry], rax
0x18000172a  cmp     [rsp+78h+FunctionEntry], 0
0x180001730  jz      short loc_180001775
0x180001732  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x18000173b  lea     rax, [rsp+78h+var_20]
0x180001740  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x180001745  lea     rax, [rsp+78h+var_18]
0x18000174a  mov     [rsp+78h+HandlerData], rax; HandlerData
0x18000174f  lea     rax, ContextRecord
0x180001756  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x18000175b  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x180001760  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x180001765  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000176a  xor     ecx, ecx; HandlerType
0x18000176c  call    cs:__imp_RtlVirtualUnwind
0x180001772  nop
0x180001773  jmp     short loc_180001798
0x180001775  mov     rax, cs:ContextRecord.Rsp
0x18000177c  mov     rax, [rax]
0x18000177f  mov     cs:ContextRecord.Rip, rax
0x180001786  mov     rax, cs:ContextRecord.Rsp
0x18000178d  add     rax, 8
0x180001791  mov     cs:ContextRecord.Rsp, rax
0x180001798  mov     rax, cs:ContextRecord.Rip
0x18000179f  mov     cs:qword_180018160, rax
0x1800017a6  mov     cs:dword_180018150, 0C0000409h
0x1800017b0  mov     cs:dword_180018154, 1
0x1800017ba  mov     cs:dword_180018168, 1
0x1800017c4  mov     eax, 8
0x1800017c9  imul    rax, 0
0x1800017cd  lea     rcx, qword_180018170
0x1800017d4  mov     qword ptr [rcx+rax], 8
0x1800017dc  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800017e3  call    __raise_securityfailure
0x1800017e8  nop
0x1800017e9  add     rsp, 78h
0x1800017ed  retn
```
