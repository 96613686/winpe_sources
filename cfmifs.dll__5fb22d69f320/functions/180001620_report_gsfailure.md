# __report_gsfailure

- ea: `0x180001620`
- end: `0x1800017c0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006030`

## callees

- `0x1800015e4`
- `0x180001620`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000167f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000167f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x1800016cc`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x1800016cc`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001660`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001660`

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
  qword_18000B240 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000B230 = -1073740791;
  dword_18000B234 = 1;
  dword_18000B248 = 3;
  qword_18000B250[0] = 2;
  qword_18000B250[1] = _security_cookie;
  qword_18000B250[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001620  mov     [rsp+arg_0], rcx
0x180001625  sub     rsp, 88h
0x18000162c  mov     [rsp+88h+ControlPc], 0
0x180001635  mov     [rsp+88h+var_30], 0
0x18000163e  mov     [rsp+88h+FunctionEntry], 0
0x180001647  mov     [rsp+88h+var_28], 0
0x180001650  mov     [rsp+88h+ImageBase], 0
0x180001659  lea     rcx, ContextRecord; ContextRecord
0x180001660  call    cs:__imp_RtlCaptureContext
0x180001666  mov     rax, cs:ContextRecord.Rip
0x18000166d  mov     [rsp+88h+ControlPc], rax
0x180001672  xor     r8d, r8d; HistoryTable
0x180001675  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000167a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000167f  call    cs:__imp_RtlLookupFunctionEntry
0x180001685  mov     [rsp+88h+FunctionEntry], rax
0x18000168a  cmp     [rsp+88h+FunctionEntry], 0
0x180001690  jz      short loc_1800016D5
0x180001692  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000169b  lea     rax, [rsp+88h+var_30]
0x1800016a0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1800016a5  lea     rax, [rsp+88h+var_28]
0x1800016aa  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1800016af  lea     rax, ContextRecord
0x1800016b6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1800016bb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1800016c0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1800016c5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800016ca  xor     ecx, ecx; HandlerType
0x1800016cc  call    cs:__imp_RtlVirtualUnwind
0x1800016d2  nop
0x1800016d3  jmp     short loc_1800016F8
0x1800016d5  mov     rax, cs:ContextRecord.Rsp
0x1800016dc  mov     rax, [rax]
0x1800016df  mov     cs:ContextRecord.Rip, rax
0x1800016e6  mov     rax, cs:ContextRecord.Rsp
0x1800016ed  add     rax, 8
0x1800016f1  mov     cs:ContextRecord.Rsp, rax
0x1800016f8  mov     rax, cs:ContextRecord.Rip
0x1800016ff  mov     cs:qword_18000B240, rax
0x180001706  mov     rax, [rsp+88h+arg_0]
0x18000170e  mov     cs:ContextRecord.Rcx, rax
0x180001715  mov     cs:dword_18000B230, 0C0000409h
0x18000171f  mov     cs:dword_18000B234, 1
0x180001729  mov     cs:dword_18000B248, 3
0x180001733  mov     eax, 8
0x180001738  imul    rax, 0
0x18000173c  lea     rcx, qword_18000B250
0x180001743  mov     qword ptr [rcx+rax], 2
0x18000174b  mov     eax, 8
0x180001750  imul    rax, 1
0x180001754  lea     rcx, qword_18000B250
0x18000175b  mov     rdx, cs:__security_cookie
0x180001762  mov     [rcx+rax], rdx
0x180001766  mov     eax, 8
0x18000176b  imul    rax, 2
0x18000176f  lea     rcx, qword_18000B250
0x180001776  mov     rdx, cs:__security_cookie_complement
0x18000177d  mov     [rcx+rax], rdx
0x180001781  mov     eax, 8
0x180001786  imul    rax, 0
0x18000178a  mov     rcx, cs:__security_cookie
0x180001791  mov     [rsp+rax+88h+var_20], rcx
0x180001796  mov     eax, 8
0x18000179b  imul    rax, 1
0x18000179f  mov     rcx, cs:__security_cookie_complement
0x1800017a6  mov     [rsp+rax+88h+var_20], rcx
0x1800017ab  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800017b2  call    __raise_securityfailure
0x1800017b7  nop
0x1800017b8  add     rsp, 88h
0x1800017bf  retn
```
