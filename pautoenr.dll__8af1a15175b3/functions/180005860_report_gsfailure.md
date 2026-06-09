# __report_gsfailure

- ea: `0x180005860`
- end: `0x180005a00`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007d20`

## callees

- `0x180005818`
- `0x180005860`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1800058bf`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1800058bf`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800058a0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800058a0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000590c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000590c`

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
  qword_18000E100 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000E0F0 = -1073740791;
  dword_18000E0F4 = 1;
  dword_18000E108 = 3;
  qword_18000E110[0] = 2;
  qword_18000E110[1] = _security_cookie;
  qword_18000E110[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180005860  mov     [rsp+arg_0], rcx
0x180005865  sub     rsp, 88h
0x18000586c  mov     [rsp+88h+ControlPc], 0
0x180005875  mov     [rsp+88h+var_30], 0
0x18000587e  mov     [rsp+88h+FunctionEntry], 0
0x180005887  mov     [rsp+88h+var_28], 0
0x180005890  mov     [rsp+88h+ImageBase], 0
0x180005899  lea     rcx, ContextRecord; ContextRecord
0x1800058a0  call    cs:__imp_RtlCaptureContext
0x1800058a6  mov     rax, cs:ContextRecord.Rip
0x1800058ad  mov     [rsp+88h+ControlPc], rax
0x1800058b2  xor     r8d, r8d; HistoryTable
0x1800058b5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800058ba  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1800058bf  call    cs:__imp_RtlLookupFunctionEntry
0x1800058c5  mov     [rsp+88h+FunctionEntry], rax
0x1800058ca  cmp     [rsp+88h+FunctionEntry], 0
0x1800058d0  jz      short loc_180005915
0x1800058d2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1800058db  lea     rax, [rsp+88h+var_30]
0x1800058e0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1800058e5  lea     rax, [rsp+88h+var_28]
0x1800058ea  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1800058ef  lea     rax, ContextRecord
0x1800058f6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1800058fb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180005900  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180005905  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000590a  xor     ecx, ecx; HandlerType
0x18000590c  call    cs:__imp_RtlVirtualUnwind
0x180005912  nop
0x180005913  jmp     short loc_180005938
0x180005915  mov     rax, cs:ContextRecord.Rsp
0x18000591c  mov     rax, [rax]
0x18000591f  mov     cs:ContextRecord.Rip, rax
0x180005926  mov     rax, cs:ContextRecord.Rsp
0x18000592d  add     rax, 8
0x180005931  mov     cs:ContextRecord.Rsp, rax
0x180005938  mov     rax, cs:ContextRecord.Rip
0x18000593f  mov     cs:qword_18000E100, rax
0x180005946  mov     rax, [rsp+88h+arg_0]
0x18000594e  mov     cs:ContextRecord.Rcx, rax
0x180005955  mov     cs:dword_18000E0F0, 0C0000409h
0x18000595f  mov     cs:dword_18000E0F4, 1
0x180005969  mov     cs:dword_18000E108, 3
0x180005973  mov     eax, 8
0x180005978  imul    rax, 0
0x18000597c  lea     rcx, qword_18000E110
0x180005983  mov     qword ptr [rcx+rax], 2
0x18000598b  mov     eax, 8
0x180005990  imul    rax, 1
0x180005994  lea     rcx, qword_18000E110
0x18000599b  mov     rdx, cs:__security_cookie
0x1800059a2  mov     [rcx+rax], rdx
0x1800059a6  mov     eax, 8
0x1800059ab  imul    rax, 2
0x1800059af  lea     rcx, qword_18000E110
0x1800059b6  mov     rdx, cs:__security_cookie_complement
0x1800059bd  mov     [rcx+rax], rdx
0x1800059c1  mov     eax, 8
0x1800059c6  imul    rax, 0
0x1800059ca  mov     rcx, cs:__security_cookie
0x1800059d1  mov     [rsp+rax+88h+var_20], rcx
0x1800059d6  mov     eax, 8
0x1800059db  imul    rax, 1
0x1800059df  mov     rcx, cs:__security_cookie_complement
0x1800059e6  mov     [rsp+rax+88h+var_20], rcx
0x1800059eb  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800059f2  call    __raise_securityfailure
0x1800059f7  nop
0x1800059f8  add     rsp, 88h
0x1800059ff  retn
```
