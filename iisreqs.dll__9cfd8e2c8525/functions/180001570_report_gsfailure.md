# __report_gsfailure

- ea: `0x180001570`
- end: `0x180001710`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002dd0`

## callees

- `0x180001534`
- `0x180001570`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800015b0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800015b0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1800015cf`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1800015cf`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000161c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000161c`

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
  qword_1800070C0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_1800070B0 = -1073740791;
  dword_1800070B4 = 1;
  dword_1800070C8 = 3;
  qword_1800070D0[0] = 2;
  qword_1800070D0[1] = _security_cookie;
  qword_1800070D0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001570  mov     [rsp+arg_0], rcx
0x180001575  sub     rsp, 88h
0x18000157c  mov     [rsp+88h+ControlPc], 0
0x180001585  mov     [rsp+88h+var_30], 0
0x18000158e  mov     [rsp+88h+FunctionEntry], 0
0x180001597  mov     [rsp+88h+var_28], 0
0x1800015a0  mov     [rsp+88h+ImageBase], 0
0x1800015a9  lea     rcx, ContextRecord; ContextRecord
0x1800015b0  call    cs:__imp_RtlCaptureContext
0x1800015b6  mov     rax, cs:ContextRecord.Rip
0x1800015bd  mov     [rsp+88h+ControlPc], rax
0x1800015c2  xor     r8d, r8d; HistoryTable
0x1800015c5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800015ca  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1800015cf  call    cs:__imp_RtlLookupFunctionEntry
0x1800015d5  mov     [rsp+88h+FunctionEntry], rax
0x1800015da  cmp     [rsp+88h+FunctionEntry], 0
0x1800015e0  jz      short loc_180001625
0x1800015e2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1800015eb  lea     rax, [rsp+88h+var_30]
0x1800015f0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1800015f5  lea     rax, [rsp+88h+var_28]
0x1800015fa  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1800015ff  lea     rax, ContextRecord
0x180001606  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000160b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001610  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001615  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000161a  xor     ecx, ecx; HandlerType
0x18000161c  call    cs:__imp_RtlVirtualUnwind
0x180001622  nop
0x180001623  jmp     short loc_180001648
0x180001625  mov     rax, cs:ContextRecord.Rsp
0x18000162c  mov     rax, [rax]
0x18000162f  mov     cs:ContextRecord.Rip, rax
0x180001636  mov     rax, cs:ContextRecord.Rsp
0x18000163d  add     rax, 8
0x180001641  mov     cs:ContextRecord.Rsp, rax
0x180001648  mov     rax, cs:ContextRecord.Rip
0x18000164f  mov     cs:qword_1800070C0, rax
0x180001656  mov     rax, [rsp+88h+arg_0]
0x18000165e  mov     cs:ContextRecord.Rcx, rax
0x180001665  mov     cs:dword_1800070B0, 0C0000409h
0x18000166f  mov     cs:dword_1800070B4, 1
0x180001679  mov     cs:dword_1800070C8, 3
0x180001683  mov     eax, 8
0x180001688  imul    rax, 0
0x18000168c  lea     rcx, qword_1800070D0
0x180001693  mov     qword ptr [rcx+rax], 2
0x18000169b  mov     eax, 8
0x1800016a0  imul    rax, 1
0x1800016a4  lea     rcx, qword_1800070D0
0x1800016ab  mov     rdx, cs:__security_cookie
0x1800016b2  mov     [rcx+rax], rdx
0x1800016b6  mov     eax, 8
0x1800016bb  imul    rax, 2
0x1800016bf  lea     rcx, qword_1800070D0
0x1800016c6  mov     rdx, cs:__security_cookie_complement
0x1800016cd  mov     [rcx+rax], rdx
0x1800016d1  mov     eax, 8
0x1800016d6  imul    rax, 0
0x1800016da  mov     rcx, cs:__security_cookie
0x1800016e1  mov     [rsp+rax+88h+var_20], rcx
0x1800016e6  mov     eax, 8
0x1800016eb  imul    rax, 1
0x1800016ef  mov     rcx, cs:__security_cookie_complement
0x1800016f6  mov     [rsp+rax+88h+var_20], rcx
0x1800016fb  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001702  call    __raise_securityfailure
0x180001707  nop
0x180001708  add     rsp, 88h
0x18000170f  retn
```
