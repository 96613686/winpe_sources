# __report_gsfailure

- ea: `0x180001710`
- end: `0x1800018b0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003650`

## callees

- `0x1800016cc`
- `0x180001710`

## import_xrefs

- `ntdll!RtlVirtualUnwind` at `0x1800017bc`
- `ntdll!RtlVirtualUnwind` at `0x1800017bc`
- `ntdll!RtlLookupFunctionEntry` at `0x18000176f`
- `ntdll!RtlLookupFunctionEntry` at `0x18000176f`
- `ntdll!RtlCaptureContext` at `0x180001750`
- `ntdll!RtlCaptureContext` at `0x180001750`

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
  qword_18001A900 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18001A8F0 = -1073740791;
  dword_18001A8F4 = 1;
  dword_18001A908 = 3;
  qword_18001A910[0] = 2;
  qword_18001A910[1] = _security_cookie;
  qword_18001A910[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001710  mov     [rsp+arg_0], rcx
0x180001715  sub     rsp, 88h
0x18000171c  mov     [rsp+88h+ControlPc], 0
0x180001725  mov     [rsp+88h+var_30], 0
0x18000172e  mov     [rsp+88h+FunctionEntry], 0
0x180001737  mov     [rsp+88h+var_28], 0
0x180001740  mov     [rsp+88h+ImageBase], 0
0x180001749  lea     rcx, ContextRecord; ContextRecord
0x180001750  call    cs:__imp_RtlCaptureContext
0x180001756  mov     rax, cs:ContextRecord.Rip
0x18000175d  mov     [rsp+88h+ControlPc], rax
0x180001762  xor     r8d, r8d; HistoryTable
0x180001765  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000176a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000176f  call    cs:__imp_RtlLookupFunctionEntry
0x180001775  mov     [rsp+88h+FunctionEntry], rax
0x18000177a  cmp     [rsp+88h+FunctionEntry], 0
0x180001780  jz      short loc_1800017C5
0x180001782  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000178b  lea     rax, [rsp+88h+var_30]
0x180001790  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001795  lea     rax, [rsp+88h+var_28]
0x18000179a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000179f  lea     rax, ContextRecord
0x1800017a6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1800017ab  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1800017b0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1800017b5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800017ba  xor     ecx, ecx; HandlerType
0x1800017bc  call    cs:__imp_RtlVirtualUnwind
0x1800017c2  nop
0x1800017c3  jmp     short loc_1800017E8
0x1800017c5  mov     rax, cs:ContextRecord.Rsp
0x1800017cc  mov     rax, [rax]
0x1800017cf  mov     cs:ContextRecord.Rip, rax
0x1800017d6  mov     rax, cs:ContextRecord.Rsp
0x1800017dd  add     rax, 8
0x1800017e1  mov     cs:ContextRecord.Rsp, rax
0x1800017e8  mov     rax, cs:ContextRecord.Rip
0x1800017ef  mov     cs:qword_18001A900, rax
0x1800017f6  mov     rax, [rsp+88h+arg_0]
0x1800017fe  mov     cs:ContextRecord.Rcx, rax
0x180001805  mov     cs:dword_18001A8F0, 0C0000409h
0x18000180f  mov     cs:dword_18001A8F4, 1
0x180001819  mov     cs:dword_18001A908, 3
0x180001823  mov     eax, 8
0x180001828  imul    rax, 0
0x18000182c  lea     rcx, qword_18001A910
0x180001833  mov     qword ptr [rcx+rax], 2
0x18000183b  mov     eax, 8
0x180001840  imul    rax, 1
0x180001844  lea     rcx, qword_18001A910
0x18000184b  mov     rdx, cs:__security_cookie
0x180001852  mov     [rcx+rax], rdx
0x180001856  mov     eax, 8
0x18000185b  imul    rax, 2
0x18000185f  lea     rcx, qword_18001A910
0x180001866  mov     rdx, cs:__security_cookie_complement
0x18000186d  mov     [rcx+rax], rdx
0x180001871  mov     eax, 8
0x180001876  imul    rax, 0
0x18000187a  mov     rcx, cs:__security_cookie
0x180001881  mov     [rsp+rax+88h+var_20], rcx
0x180001886  mov     eax, 8
0x18000188b  imul    rax, 1
0x18000188f  mov     rcx, cs:__security_cookie_complement
0x180001896  mov     [rsp+rax+88h+var_20], rcx
0x18000189b  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800018a2  call    __raise_securityfailure
0x1800018a7  nop
0x1800018a8  add     rsp, 88h
0x1800018af  retn
```
