# __report_gsfailure

- ea: `0x1800016c0`
- end: `0x180001860`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008e30`

## callees

- `0x180001684`
- `0x1800016c0`

## import_xrefs

- `ntdll!RtlLookupFunctionEntry` at `0x18000171f`
- `ntdll!RtlLookupFunctionEntry` at `0x18000171f`
- `ntdll!RtlVirtualUnwind` at `0x18000176c`
- `ntdll!RtlVirtualUnwind` at `0x18000176c`
- `ntdll!RtlCaptureContext` at `0x180001700`
- `ntdll!RtlCaptureContext` at `0x180001700`

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
  qword_180010280 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_180010270 = -1073740791;
  dword_180010274 = 1;
  dword_180010288 = 3;
  qword_180010290[0] = 2;
  qword_180010290[1] = _security_cookie;
  qword_180010290[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800016c0  mov     [rsp+arg_0], rcx
0x1800016c5  sub     rsp, 88h
0x1800016cc  mov     [rsp+88h+ControlPc], 0
0x1800016d5  mov     [rsp+88h+var_30], 0
0x1800016de  mov     [rsp+88h+FunctionEntry], 0
0x1800016e7  mov     [rsp+88h+var_28], 0
0x1800016f0  mov     [rsp+88h+ImageBase], 0
0x1800016f9  lea     rcx, ContextRecord; ContextRecord
0x180001700  call    cs:__imp_RtlCaptureContext
0x180001706  mov     rax, cs:ContextRecord.Rip
0x18000170d  mov     [rsp+88h+ControlPc], rax
0x180001712  xor     r8d, r8d; HistoryTable
0x180001715  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000171a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000171f  call    cs:__imp_RtlLookupFunctionEntry
0x180001725  mov     [rsp+88h+FunctionEntry], rax
0x18000172a  cmp     [rsp+88h+FunctionEntry], 0
0x180001730  jz      short loc_180001775
0x180001732  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000173b  lea     rax, [rsp+88h+var_30]
0x180001740  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001745  lea     rax, [rsp+88h+var_28]
0x18000174a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000174f  lea     rax, ContextRecord
0x180001756  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000175b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001760  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001765  mov     rdx, [rsp+88h+ImageBase]; ImageBase
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
0x18000179f  mov     cs:qword_180010280, rax
0x1800017a6  mov     rax, [rsp+88h+arg_0]
0x1800017ae  mov     cs:ContextRecord.Rcx, rax
0x1800017b5  mov     cs:dword_180010270, 0C0000409h
0x1800017bf  mov     cs:dword_180010274, 1
0x1800017c9  mov     cs:dword_180010288, 3
0x1800017d3  mov     eax, 8
0x1800017d8  imul    rax, 0
0x1800017dc  lea     rcx, qword_180010290
0x1800017e3  mov     qword ptr [rcx+rax], 2
0x1800017eb  mov     eax, 8
0x1800017f0  imul    rax, 1
0x1800017f4  lea     rcx, qword_180010290
0x1800017fb  mov     rdx, cs:__security_cookie
0x180001802  mov     [rcx+rax], rdx
0x180001806  mov     eax, 8
0x18000180b  imul    rax, 2
0x18000180f  lea     rcx, qword_180010290
0x180001816  mov     rdx, cs:__security_cookie_complement
0x18000181d  mov     [rcx+rax], rdx
0x180001821  mov     eax, 8
0x180001826  imul    rax, 0
0x18000182a  mov     rcx, cs:__security_cookie
0x180001831  mov     [rsp+rax+88h+var_20], rcx
0x180001836  mov     eax, 8
0x18000183b  imul    rax, 1
0x18000183f  mov     rcx, cs:__security_cookie_complement
0x180001846  mov     [rsp+rax+88h+var_20], rcx
0x18000184b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001852  call    __raise_securityfailure
0x180001857  nop
0x180001858  add     rsp, 88h
0x18000185f  retn
```
