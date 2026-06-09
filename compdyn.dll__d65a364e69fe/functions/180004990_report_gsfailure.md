# __report_gsfailure

- ea: `0x180004990`
- end: `0x180004b30`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004c10`

## callees

- `0x18000494c`
- `0x180004990`

## import_xrefs

- `ntdll!RtlVirtualUnwind` at `0x180004a3c`
- `ntdll!RtlVirtualUnwind` at `0x180004a3c`
- `ntdll!RtlLookupFunctionEntry` at `0x1800049ef`
- `ntdll!RtlLookupFunctionEntry` at `0x1800049ef`
- `ntdll!RtlCaptureContext` at `0x1800049d0`
- `ntdll!RtlCaptureContext` at `0x1800049d0`

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
  qword_18000D0E0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000D0D0 = -1073740791;
  dword_18000D0D4 = 1;
  dword_18000D0E8 = 3;
  qword_18000D0F0[0] = 2;
  qword_18000D0F0[1] = _security_cookie;
  qword_18000D0F0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180004990  mov     [rsp+arg_0], rcx
0x180004995  sub     rsp, 88h
0x18000499c  mov     [rsp+88h+ControlPc], 0
0x1800049a5  mov     [rsp+88h+var_30], 0
0x1800049ae  mov     [rsp+88h+FunctionEntry], 0
0x1800049b7  mov     [rsp+88h+var_28], 0
0x1800049c0  mov     [rsp+88h+ImageBase], 0
0x1800049c9  lea     rcx, ContextRecord; ContextRecord
0x1800049d0  call    cs:__imp_RtlCaptureContext
0x1800049d6  mov     rax, cs:ContextRecord.Rip
0x1800049dd  mov     [rsp+88h+ControlPc], rax
0x1800049e2  xor     r8d, r8d; HistoryTable
0x1800049e5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800049ea  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1800049ef  call    cs:__imp_RtlLookupFunctionEntry
0x1800049f5  mov     [rsp+88h+FunctionEntry], rax
0x1800049fa  cmp     [rsp+88h+FunctionEntry], 0
0x180004a00  jz      short loc_180004A45
0x180004a02  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x180004a0b  lea     rax, [rsp+88h+var_30]
0x180004a10  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180004a15  lea     rax, [rsp+88h+var_28]
0x180004a1a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x180004a1f  lea     rax, ContextRecord
0x180004a26  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x180004a2b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180004a30  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180004a35  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x180004a3a  xor     ecx, ecx; HandlerType
0x180004a3c  call    cs:__imp_RtlVirtualUnwind
0x180004a42  nop
0x180004a43  jmp     short loc_180004A68
0x180004a45  mov     rax, cs:ContextRecord.Rsp
0x180004a4c  mov     rax, [rax]
0x180004a4f  mov     cs:ContextRecord.Rip, rax
0x180004a56  mov     rax, cs:ContextRecord.Rsp
0x180004a5d  add     rax, 8
0x180004a61  mov     cs:ContextRecord.Rsp, rax
0x180004a68  mov     rax, cs:ContextRecord.Rip
0x180004a6f  mov     cs:qword_18000D0E0, rax
0x180004a76  mov     rax, [rsp+88h+arg_0]
0x180004a7e  mov     cs:ContextRecord.Rcx, rax
0x180004a85  mov     cs:dword_18000D0D0, 0C0000409h
0x180004a8f  mov     cs:dword_18000D0D4, 1
0x180004a99  mov     cs:dword_18000D0E8, 3
0x180004aa3  mov     eax, 8
0x180004aa8  imul    rax, 0
0x180004aac  lea     rcx, qword_18000D0F0
0x180004ab3  mov     qword ptr [rcx+rax], 2
0x180004abb  mov     eax, 8
0x180004ac0  imul    rax, 1
0x180004ac4  lea     rcx, qword_18000D0F0
0x180004acb  mov     rdx, cs:__security_cookie
0x180004ad2  mov     [rcx+rax], rdx
0x180004ad6  mov     eax, 8
0x180004adb  imul    rax, 2
0x180004adf  lea     rcx, qword_18000D0F0
0x180004ae6  mov     rdx, cs:__security_cookie_complement
0x180004aed  mov     [rcx+rax], rdx
0x180004af1  mov     eax, 8
0x180004af6  imul    rax, 0
0x180004afa  mov     rcx, cs:__security_cookie
0x180004b01  mov     [rsp+rax+88h+var_20], rcx
0x180004b06  mov     eax, 8
0x180004b0b  imul    rax, 1
0x180004b0f  mov     rcx, cs:__security_cookie_complement
0x180004b16  mov     [rsp+rax+88h+var_20], rcx
0x180004b1b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180004b22  call    __raise_securityfailure
0x180004b27  nop
0x180004b28  add     rsp, 88h
0x180004b2f  retn
```
