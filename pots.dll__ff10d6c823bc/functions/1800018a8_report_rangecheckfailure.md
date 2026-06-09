# __report_rangecheckfailure

- ea: `0x1800018a8`
- end: `0x1800019ce`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003d30`
- `0x180003eb0`
- `0x180004240`

## callees

- `0x1800016b8`
- `0x1800018a8`

## import_xrefs

- `ntdll!RtlLookupFunctionEntry` at `0x1800018ff`
- `ntdll!RtlLookupFunctionEntry` at `0x1800018ff`
- `ntdll!RtlCaptureContext` at `0x1800018e0`
- `ntdll!RtlCaptureContext` at `0x1800018e0`
- `ntdll!RtlVirtualUnwind` at `0x18000194c`
- `ntdll!RtlVirtualUnwind` at `0x18000194c`

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
  qword_1800092C0 = ContextRecord.Rip;
  dword_1800092B0 = -1073740791;
  dword_1800092B4 = 1;
  dword_1800092C8 = 1;
  unk_1800092D0 = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800018a8  sub     rsp, 78h
0x1800018ac  mov     [rsp+78h+ControlPc], 0
0x1800018b5  mov     [rsp+78h+var_20], 0
0x1800018be  mov     [rsp+78h+FunctionEntry], 0
0x1800018c7  mov     [rsp+78h+var_18], 0
0x1800018d0  mov     [rsp+78h+ImageBase], 0
0x1800018d9  lea     rcx, ContextRecord; ContextRecord
0x1800018e0  call    cs:__imp_RtlCaptureContext
0x1800018e6  mov     rax, cs:ContextRecord.Rip
0x1800018ed  mov     [rsp+78h+ControlPc], rax
0x1800018f2  xor     r8d, r8d; HistoryTable
0x1800018f5  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x1800018fa  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x1800018ff  call    cs:__imp_RtlLookupFunctionEntry
0x180001905  mov     [rsp+78h+FunctionEntry], rax
0x18000190a  cmp     [rsp+78h+FunctionEntry], 0
0x180001910  jz      short loc_180001955
0x180001912  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x18000191b  lea     rax, [rsp+78h+var_20]
0x180001920  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x180001925  lea     rax, [rsp+78h+var_18]
0x18000192a  mov     [rsp+78h+HandlerData], rax; HandlerData
0x18000192f  lea     rax, ContextRecord
0x180001936  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x18000193b  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x180001940  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x180001945  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000194a  xor     ecx, ecx; HandlerType
0x18000194c  call    cs:__imp_RtlVirtualUnwind
0x180001952  nop
0x180001953  jmp     short loc_180001978
0x180001955  mov     rax, cs:ContextRecord.Rsp
0x18000195c  mov     rax, [rax]
0x18000195f  mov     cs:ContextRecord.Rip, rax
0x180001966  mov     rax, cs:ContextRecord.Rsp
0x18000196d  add     rax, 8
0x180001971  mov     cs:ContextRecord.Rsp, rax
0x180001978  mov     rax, cs:ContextRecord.Rip
0x18000197f  mov     cs:qword_1800092C0, rax
0x180001986  mov     cs:dword_1800092B0, 0C0000409h
0x180001990  mov     cs:dword_1800092B4, 1
0x18000199a  mov     cs:dword_1800092C8, 1
0x1800019a4  mov     eax, 8
0x1800019a9  imul    rax, 0
0x1800019ad  lea     rcx, unk_1800092D0
0x1800019b4  mov     qword ptr [rcx+rax], 8
0x1800019bc  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800019c3  call    __raise_securityfailure
0x1800019c8  nop
0x1800019c9  add     rsp, 78h
0x1800019cd  retn
```
