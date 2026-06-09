# __report_gsfailure

- ea: `0x180001720`
- end: `0x1800018c0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002da0`

## callees

- `0x1800016dc`
- `0x180001720`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001760`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001760`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000177f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000177f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x1800017cc`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x1800017cc`

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
  qword_180007EC0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_180007EB0 = -1073740791;
  dword_180007EB4 = 1;
  dword_180007EC8 = 3;
  qword_180007ED0[0] = 2;
  qword_180007ED0[1] = _security_cookie;
  qword_180007ED0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001720  mov     [rsp+arg_0], rcx
0x180001725  sub     rsp, 88h
0x18000172c  mov     [rsp+88h+ControlPc], 0
0x180001735  mov     [rsp+88h+var_30], 0
0x18000173e  mov     [rsp+88h+FunctionEntry], 0
0x180001747  mov     [rsp+88h+var_28], 0
0x180001750  mov     [rsp+88h+ImageBase], 0
0x180001759  lea     rcx, ContextRecord; ContextRecord
0x180001760  call    cs:__imp_RtlCaptureContext
0x180001766  mov     rax, cs:ContextRecord.Rip
0x18000176d  mov     [rsp+88h+ControlPc], rax
0x180001772  xor     r8d, r8d; HistoryTable
0x180001775  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000177a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000177f  call    cs:__imp_RtlLookupFunctionEntry
0x180001785  mov     [rsp+88h+FunctionEntry], rax
0x18000178a  cmp     [rsp+88h+FunctionEntry], 0
0x180001790  jz      short loc_1800017D5
0x180001792  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000179b  lea     rax, [rsp+88h+var_30]
0x1800017a0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1800017a5  lea     rax, [rsp+88h+var_28]
0x1800017aa  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1800017af  lea     rax, ContextRecord
0x1800017b6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1800017bb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1800017c0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1800017c5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800017ca  xor     ecx, ecx; HandlerType
0x1800017cc  call    cs:__imp_RtlVirtualUnwind
0x1800017d2  nop
0x1800017d3  jmp     short loc_1800017F8
0x1800017d5  mov     rax, cs:ContextRecord.Rsp
0x1800017dc  mov     rax, [rax]
0x1800017df  mov     cs:ContextRecord.Rip, rax
0x1800017e6  mov     rax, cs:ContextRecord.Rsp
0x1800017ed  add     rax, 8
0x1800017f1  mov     cs:ContextRecord.Rsp, rax
0x1800017f8  mov     rax, cs:ContextRecord.Rip
0x1800017ff  mov     cs:qword_180007EC0, rax
0x180001806  mov     rax, [rsp+88h+arg_0]
0x18000180e  mov     cs:ContextRecord.Rcx, rax
0x180001815  mov     cs:dword_180007EB0, 0C0000409h
0x18000181f  mov     cs:dword_180007EB4, 1
0x180001829  mov     cs:dword_180007EC8, 3
0x180001833  mov     eax, 8
0x180001838  imul    rax, 0
0x18000183c  lea     rcx, qword_180007ED0
0x180001843  mov     qword ptr [rcx+rax], 2
0x18000184b  mov     eax, 8
0x180001850  imul    rax, 1
0x180001854  lea     rcx, qword_180007ED0
0x18000185b  mov     rdx, cs:__security_cookie
0x180001862  mov     [rcx+rax], rdx
0x180001866  mov     eax, 8
0x18000186b  imul    rax, 2
0x18000186f  lea     rcx, qword_180007ED0
0x180001876  mov     rdx, cs:__security_cookie_complement
0x18000187d  mov     [rcx+rax], rdx
0x180001881  mov     eax, 8
0x180001886  imul    rax, 0
0x18000188a  mov     rcx, cs:__security_cookie
0x180001891  mov     [rsp+rax+88h+var_20], rcx
0x180001896  mov     eax, 8
0x18000189b  imul    rax, 1
0x18000189f  mov     rcx, cs:__security_cookie_complement
0x1800018a6  mov     [rsp+rax+88h+var_20], rcx
0x1800018ab  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800018b2  call    __raise_securityfailure
0x1800018b7  nop
0x1800018b8  add     rsp, 88h
0x1800018bf  retn
```
