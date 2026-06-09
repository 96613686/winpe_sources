# __report_gsfailure

- ea: `0x180001780`
- end: `0x180001920`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800067c0`

## callees

- `0x180001740`
- `0x180001780`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x1800017c0`
- `ntdll!RtlCaptureContext` at `0x1800017c0`
- `ntdll!RtlLookupFunctionEntry` at `0x1800017df`
- `ntdll!RtlLookupFunctionEntry` at `0x1800017df`
- `ntdll!RtlVirtualUnwind` at `0x18000182c`
- `ntdll!RtlVirtualUnwind` at `0x18000182c`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  struct _RUNTIME_FUNCTION *FunctionEntry; // [rsp+40h] [rbp-48h]
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
  qword_18000B0C0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000B0B0 = -1073740791;
  dword_18000B0B4 = 1;
  dword_18000B0C8 = 3;
  qword_18000B0D0[0] = 2;
  qword_18000B0D0[1] = _security_cookie;
  qword_18000B0D0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001780  mov     [rsp+arg_0], rcx
0x180001785  sub     rsp, 88h
0x18000178c  mov     [rsp+88h+ControlPc], 0
0x180001795  mov     [rsp+88h+var_30], 0
0x18000179e  mov     [rsp+88h+FunctionEntry], 0
0x1800017a7  mov     [rsp+88h+var_28], 0
0x1800017b0  mov     [rsp+88h+ImageBase], 0
0x1800017b9  lea     rcx, ContextRecord; ContextRecord
0x1800017c0  call    cs:__imp_RtlCaptureContext
0x1800017c6  mov     rax, cs:ContextRecord.Rip
0x1800017cd  mov     [rsp+88h+ControlPc], rax
0x1800017d2  xor     r8d, r8d; HistoryTable
0x1800017d5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800017da  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1800017df  call    cs:__imp_RtlLookupFunctionEntry
0x1800017e5  mov     [rsp+88h+FunctionEntry], rax
0x1800017ea  cmp     [rsp+88h+FunctionEntry], 0
0x1800017f0  jz      short loc_180001835
0x1800017f2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1800017fb  lea     rax, [rsp+88h+var_30]
0x180001800  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001805  lea     rax, [rsp+88h+var_28]
0x18000180a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000180f  lea     rax, ContextRecord
0x180001816  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000181b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001820  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001825  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000182a  xor     ecx, ecx; HandlerType
0x18000182c  call    cs:__imp_RtlVirtualUnwind
0x180001832  nop
0x180001833  jmp     short loc_180001858
0x180001835  mov     rax, cs:ContextRecord.Rsp
0x18000183c  mov     rax, [rax]
0x18000183f  mov     cs:ContextRecord.Rip, rax
0x180001846  mov     rax, cs:ContextRecord.Rsp
0x18000184d  add     rax, 8
0x180001851  mov     cs:ContextRecord.Rsp, rax
0x180001858  mov     rax, cs:ContextRecord.Rip
0x18000185f  mov     cs:qword_18000B0C0, rax
0x180001866  mov     rax, [rsp+88h+arg_0]
0x18000186e  mov     cs:ContextRecord.Rcx, rax
0x180001875  mov     cs:dword_18000B0B0, 0C0000409h
0x18000187f  mov     cs:dword_18000B0B4, 1
0x180001889  mov     cs:dword_18000B0C8, 3
0x180001893  mov     eax, 8
0x180001898  imul    rax, 0
0x18000189c  lea     rcx, qword_18000B0D0
0x1800018a3  mov     qword ptr [rcx+rax], 2
0x1800018ab  mov     eax, 8
0x1800018b0  imul    rax, 1
0x1800018b4  lea     rcx, qword_18000B0D0
0x1800018bb  mov     rdx, cs:__security_cookie
0x1800018c2  mov     [rcx+rax], rdx
0x1800018c6  mov     eax, 8
0x1800018cb  imul    rax, 2
0x1800018cf  lea     rcx, qword_18000B0D0
0x1800018d6  mov     rdx, cs:__security_cookie_complement
0x1800018dd  mov     [rcx+rax], rdx
0x1800018e1  mov     eax, 8
0x1800018e6  imul    rax, 0
0x1800018ea  mov     rcx, cs:__security_cookie
0x1800018f1  mov     [rsp+rax+88h+var_20], rcx
0x1800018f6  mov     eax, 8
0x1800018fb  imul    rax, 1
0x1800018ff  mov     rcx, cs:__security_cookie_complement
0x180001906  mov     [rsp+rax+88h+var_20], rcx
0x18000190b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001912  call    __raise_securityfailure
0x180001917  nop
0x180001918  add     rsp, 88h
0x18000191f  retn
```
