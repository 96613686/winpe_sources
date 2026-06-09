# __report_gsfailure

- ea: `0x1800054e0`
- end: `0x180005680`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006b00`

## callees

- `0x180005498`
- `0x1800054e0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000558c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000558c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180005520`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180005520`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000553f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000553f`

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
  qword_18000A0C0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000A0B0 = -1073740791;
  dword_18000A0B4 = 1;
  dword_18000A0C8 = 3;
  qword_18000A0D0[0] = 2;
  qword_18000A0D0[1] = _security_cookie;
  qword_18000A0D0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800054e0  mov     [rsp+arg_0], rcx
0x1800054e5  sub     rsp, 88h
0x1800054ec  mov     [rsp+88h+ControlPc], 0
0x1800054f5  mov     [rsp+88h+var_30], 0
0x1800054fe  mov     [rsp+88h+FunctionEntry], 0
0x180005507  mov     [rsp+88h+var_28], 0
0x180005510  mov     [rsp+88h+ImageBase], 0
0x180005519  lea     rcx, ContextRecord; ContextRecord
0x180005520  call    cs:__imp_RtlCaptureContext
0x180005526  mov     rax, cs:ContextRecord.Rip
0x18000552d  mov     [rsp+88h+ControlPc], rax
0x180005532  xor     r8d, r8d; HistoryTable
0x180005535  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000553a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000553f  call    cs:__imp_RtlLookupFunctionEntry
0x180005545  mov     [rsp+88h+FunctionEntry], rax
0x18000554a  cmp     [rsp+88h+FunctionEntry], 0
0x180005550  jz      short loc_180005595
0x180005552  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000555b  lea     rax, [rsp+88h+var_30]
0x180005560  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180005565  lea     rax, [rsp+88h+var_28]
0x18000556a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000556f  lea     rax, ContextRecord
0x180005576  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000557b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180005580  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180005585  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000558a  xor     ecx, ecx; HandlerType
0x18000558c  call    cs:__imp_RtlVirtualUnwind
0x180005592  nop
0x180005593  jmp     short loc_1800055B8
0x180005595  mov     rax, cs:ContextRecord.Rsp
0x18000559c  mov     rax, [rax]
0x18000559f  mov     cs:ContextRecord.Rip, rax
0x1800055a6  mov     rax, cs:ContextRecord.Rsp
0x1800055ad  add     rax, 8
0x1800055b1  mov     cs:ContextRecord.Rsp, rax
0x1800055b8  mov     rax, cs:ContextRecord.Rip
0x1800055bf  mov     cs:qword_18000A0C0, rax
0x1800055c6  mov     rax, [rsp+88h+arg_0]
0x1800055ce  mov     cs:ContextRecord.Rcx, rax
0x1800055d5  mov     cs:dword_18000A0B0, 0C0000409h
0x1800055df  mov     cs:dword_18000A0B4, 1
0x1800055e9  mov     cs:dword_18000A0C8, 3
0x1800055f3  mov     eax, 8
0x1800055f8  imul    rax, 0
0x1800055fc  lea     rcx, qword_18000A0D0
0x180005603  mov     qword ptr [rcx+rax], 2
0x18000560b  mov     eax, 8
0x180005610  imul    rax, 1
0x180005614  lea     rcx, qword_18000A0D0
0x18000561b  mov     rdx, cs:__security_cookie
0x180005622  mov     [rcx+rax], rdx
0x180005626  mov     eax, 8
0x18000562b  imul    rax, 2
0x18000562f  lea     rcx, qword_18000A0D0
0x180005636  mov     rdx, cs:__security_cookie_complement
0x18000563d  mov     [rcx+rax], rdx
0x180005641  mov     eax, 8
0x180005646  imul    rax, 0
0x18000564a  mov     rcx, cs:__security_cookie
0x180005651  mov     [rsp+rax+88h+var_20], rcx
0x180005656  mov     eax, 8
0x18000565b  imul    rax, 1
0x18000565f  mov     rcx, cs:__security_cookie_complement
0x180005666  mov     [rsp+rax+88h+var_20], rcx
0x18000566b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180005672  call    __raise_securityfailure
0x180005677  nop
0x180005678  add     rsp, 88h
0x18000567f  retn
```
