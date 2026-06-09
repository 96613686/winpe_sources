# __report_gsfailure

- ea: `0x1800017a0`
- end: `0x180001940`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800054f0`

## callees

- `0x18000175c`
- `0x1800017a0`

## import_xrefs

- `KERNEL32!RtlVirtualUnwind` at `0x18000184c`
- `KERNEL32!RtlVirtualUnwind` at `0x18000184c`
- `KERNEL32!RtlLookupFunctionEntry` at `0x1800017ff`
- `KERNEL32!RtlLookupFunctionEntry` at `0x1800017ff`
- `KERNEL32!RtlCaptureContext` at `0x1800017e0`
- `KERNEL32!RtlCaptureContext` at `0x1800017e0`

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
0x1800017a0  mov     [rsp+arg_0], rcx
0x1800017a5  sub     rsp, 88h
0x1800017ac  mov     [rsp+88h+ControlPc], 0
0x1800017b5  mov     [rsp+88h+var_30], 0
0x1800017be  mov     [rsp+88h+FunctionEntry], 0
0x1800017c7  mov     [rsp+88h+var_28], 0
0x1800017d0  mov     [rsp+88h+ImageBase], 0
0x1800017d9  lea     rcx, ContextRecord; ContextRecord
0x1800017e0  call    cs:__imp_RtlCaptureContext
0x1800017e6  mov     rax, cs:ContextRecord.Rip
0x1800017ed  mov     [rsp+88h+ControlPc], rax
0x1800017f2  xor     r8d, r8d; HistoryTable
0x1800017f5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800017fa  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1800017ff  call    cs:__imp_RtlLookupFunctionEntry
0x180001805  mov     [rsp+88h+FunctionEntry], rax
0x18000180a  cmp     [rsp+88h+FunctionEntry], 0
0x180001810  jz      short loc_180001855
0x180001812  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000181b  lea     rax, [rsp+88h+var_30]
0x180001820  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001825  lea     rax, [rsp+88h+var_28]
0x18000182a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000182f  lea     rax, ContextRecord
0x180001836  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000183b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001840  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001845  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000184a  xor     ecx, ecx; HandlerType
0x18000184c  call    cs:__imp_RtlVirtualUnwind
0x180001852  nop
0x180001853  jmp     short loc_180001878
0x180001855  mov     rax, cs:ContextRecord.Rsp
0x18000185c  mov     rax, [rax]
0x18000185f  mov     cs:ContextRecord.Rip, rax
0x180001866  mov     rax, cs:ContextRecord.Rsp
0x18000186d  add     rax, 8
0x180001871  mov     cs:ContextRecord.Rsp, rax
0x180001878  mov     rax, cs:ContextRecord.Rip
0x18000187f  mov     cs:qword_1800090C0, rax
0x180001886  mov     rax, [rsp+88h+arg_0]
0x18000188e  mov     cs:ContextRecord.Rcx, rax
0x180001895  mov     cs:dword_1800090B0, 0C0000409h
0x18000189f  mov     cs:dword_1800090B4, 1
0x1800018a9  mov     cs:dword_1800090C8, 3
0x1800018b3  mov     eax, 8
0x1800018b8  imul    rax, 0
0x1800018bc  lea     rcx, qword_1800090D0
0x1800018c3  mov     qword ptr [rcx+rax], 2
0x1800018cb  mov     eax, 8
0x1800018d0  imul    rax, 1
0x1800018d4  lea     rcx, qword_1800090D0
0x1800018db  mov     rdx, cs:__security_cookie
0x1800018e2  mov     [rcx+rax], rdx
0x1800018e6  mov     eax, 8
0x1800018eb  imul    rax, 2
0x1800018ef  lea     rcx, qword_1800090D0
0x1800018f6  mov     rdx, cs:__security_cookie_complement
0x1800018fd  mov     [rcx+rax], rdx
0x180001901  mov     eax, 8
0x180001906  imul    rax, 0
0x18000190a  mov     rcx, cs:__security_cookie
0x180001911  mov     [rsp+rax+88h+var_20], rcx
0x180001916  mov     eax, 8
0x18000191b  imul    rax, 1
0x18000191f  mov     rcx, cs:__security_cookie_complement
0x180001926  mov     [rsp+rax+88h+var_20], rcx
0x18000192b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001932  call    __raise_securityfailure
0x180001937  nop
0x180001938  add     rsp, 88h
0x18000193f  retn
```
