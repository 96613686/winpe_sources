# __report_gsfailure

- ea: `0x180003c30`
- end: `0x180003dd0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005750`

## callees

- `0x180003be8`
- `0x180003c30`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180003c8f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180003c8f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x180003cdc`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x180003cdc`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180003c70`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180003c70`

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
0x180003c30  mov     [rsp+arg_0], rcx
0x180003c35  sub     rsp, 88h
0x180003c3c  mov     [rsp+88h+ControlPc], 0
0x180003c45  mov     [rsp+88h+var_30], 0
0x180003c4e  mov     [rsp+88h+FunctionEntry], 0
0x180003c57  mov     [rsp+88h+var_28], 0
0x180003c60  mov     [rsp+88h+ImageBase], 0
0x180003c69  lea     rcx, ContextRecord; ContextRecord
0x180003c70  call    cs:__imp_RtlCaptureContext
0x180003c76  mov     rax, cs:ContextRecord.Rip
0x180003c7d  mov     [rsp+88h+ControlPc], rax
0x180003c82  xor     r8d, r8d; HistoryTable
0x180003c85  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x180003c8a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x180003c8f  call    cs:__imp_RtlLookupFunctionEntry
0x180003c95  mov     [rsp+88h+FunctionEntry], rax
0x180003c9a  cmp     [rsp+88h+FunctionEntry], 0
0x180003ca0  jz      short loc_180003CE5
0x180003ca2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x180003cab  lea     rax, [rsp+88h+var_30]
0x180003cb0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180003cb5  lea     rax, [rsp+88h+var_28]
0x180003cba  mov     [rsp+88h+HandlerData], rax; HandlerData
0x180003cbf  lea     rax, ContextRecord
0x180003cc6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x180003ccb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180003cd0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180003cd5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x180003cda  xor     ecx, ecx; HandlerType
0x180003cdc  call    cs:__imp_RtlVirtualUnwind
0x180003ce2  nop
0x180003ce3  jmp     short loc_180003D08
0x180003ce5  mov     rax, cs:ContextRecord.Rsp
0x180003cec  mov     rax, [rax]
0x180003cef  mov     cs:ContextRecord.Rip, rax
0x180003cf6  mov     rax, cs:ContextRecord.Rsp
0x180003cfd  add     rax, 8
0x180003d01  mov     cs:ContextRecord.Rsp, rax
0x180003d08  mov     rax, cs:ContextRecord.Rip
0x180003d0f  mov     cs:qword_1800090C0, rax
0x180003d16  mov     rax, [rsp+88h+arg_0]
0x180003d1e  mov     cs:ContextRecord.Rcx, rax
0x180003d25  mov     cs:dword_1800090B0, 0C0000409h
0x180003d2f  mov     cs:dword_1800090B4, 1
0x180003d39  mov     cs:dword_1800090C8, 3
0x180003d43  mov     eax, 8
0x180003d48  imul    rax, 0
0x180003d4c  lea     rcx, qword_1800090D0
0x180003d53  mov     qword ptr [rcx+rax], 2
0x180003d5b  mov     eax, 8
0x180003d60  imul    rax, 1
0x180003d64  lea     rcx, qword_1800090D0
0x180003d6b  mov     rdx, cs:__security_cookie
0x180003d72  mov     [rcx+rax], rdx
0x180003d76  mov     eax, 8
0x180003d7b  imul    rax, 2
0x180003d7f  lea     rcx, qword_1800090D0
0x180003d86  mov     rdx, cs:__security_cookie_complement
0x180003d8d  mov     [rcx+rax], rdx
0x180003d91  mov     eax, 8
0x180003d96  imul    rax, 0
0x180003d9a  mov     rcx, cs:__security_cookie
0x180003da1  mov     [rsp+rax+88h+var_20], rcx
0x180003da6  mov     eax, 8
0x180003dab  imul    rax, 1
0x180003daf  mov     rcx, cs:__security_cookie_complement
0x180003db6  mov     [rsp+rax+88h+var_20], rcx
0x180003dbb  lea     rcx, ExceptionInfo; ExceptionInfo
0x180003dc2  call    __raise_securityfailure
0x180003dc7  nop
0x180003dc8  add     rsp, 88h
0x180003dcf  retn
```
