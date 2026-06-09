# __report_gsfailure

- ea: `0x180005be0`
- end: `0x180005d80`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005f90`

## callees

- `0x180005b9c`
- `0x180005be0`

## import_xrefs

- `ntdll!RtlVirtualUnwind` at `0x180005c8c`
- `ntdll!RtlVirtualUnwind` at `0x180005c8c`
- `ntdll!RtlLookupFunctionEntry` at `0x180005c3f`
- `ntdll!RtlLookupFunctionEntry` at `0x180005c3f`
- `ntdll!RtlCaptureContext` at `0x180005c20`
- `ntdll!RtlCaptureContext` at `0x180005c20`

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
  qword_18000F0E0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000F0D0 = -1073740791;
  dword_18000F0D4 = 1;
  dword_18000F0E8 = 3;
  qword_18000F0F0[0] = 2;
  qword_18000F0F0[1] = _security_cookie;
  qword_18000F0F0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180005be0  mov     [rsp+arg_0], rcx
0x180005be5  sub     rsp, 88h
0x180005bec  mov     [rsp+88h+ControlPc], 0
0x180005bf5  mov     [rsp+88h+var_30], 0
0x180005bfe  mov     [rsp+88h+FunctionEntry], 0
0x180005c07  mov     [rsp+88h+var_28], 0
0x180005c10  mov     [rsp+88h+ImageBase], 0
0x180005c19  lea     rcx, ContextRecord; ContextRecord
0x180005c20  call    cs:__imp_RtlCaptureContext
0x180005c26  mov     rax, cs:ContextRecord.Rip
0x180005c2d  mov     [rsp+88h+ControlPc], rax
0x180005c32  xor     r8d, r8d; HistoryTable
0x180005c35  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x180005c3a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x180005c3f  call    cs:__imp_RtlLookupFunctionEntry
0x180005c45  mov     [rsp+88h+FunctionEntry], rax
0x180005c4a  cmp     [rsp+88h+FunctionEntry], 0
0x180005c50  jz      short loc_180005C95
0x180005c52  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x180005c5b  lea     rax, [rsp+88h+var_30]
0x180005c60  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180005c65  lea     rax, [rsp+88h+var_28]
0x180005c6a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x180005c6f  lea     rax, ContextRecord
0x180005c76  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x180005c7b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180005c80  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180005c85  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x180005c8a  xor     ecx, ecx; HandlerType
0x180005c8c  call    cs:__imp_RtlVirtualUnwind
0x180005c92  nop
0x180005c93  jmp     short loc_180005CB8
0x180005c95  mov     rax, cs:ContextRecord.Rsp
0x180005c9c  mov     rax, [rax]
0x180005c9f  mov     cs:ContextRecord.Rip, rax
0x180005ca6  mov     rax, cs:ContextRecord.Rsp
0x180005cad  add     rax, 8
0x180005cb1  mov     cs:ContextRecord.Rsp, rax
0x180005cb8  mov     rax, cs:ContextRecord.Rip
0x180005cbf  mov     cs:qword_18000F0E0, rax
0x180005cc6  mov     rax, [rsp+88h+arg_0]
0x180005cce  mov     cs:ContextRecord.Rcx, rax
0x180005cd5  mov     cs:dword_18000F0D0, 0C0000409h
0x180005cdf  mov     cs:dword_18000F0D4, 1
0x180005ce9  mov     cs:dword_18000F0E8, 3
0x180005cf3  mov     eax, 8
0x180005cf8  imul    rax, 0
0x180005cfc  lea     rcx, qword_18000F0F0
0x180005d03  mov     qword ptr [rcx+rax], 2
0x180005d0b  mov     eax, 8
0x180005d10  imul    rax, 1
0x180005d14  lea     rcx, qword_18000F0F0
0x180005d1b  mov     rdx, cs:__security_cookie
0x180005d22  mov     [rcx+rax], rdx
0x180005d26  mov     eax, 8
0x180005d2b  imul    rax, 2
0x180005d2f  lea     rcx, qword_18000F0F0
0x180005d36  mov     rdx, cs:__security_cookie_complement
0x180005d3d  mov     [rcx+rax], rdx
0x180005d41  mov     eax, 8
0x180005d46  imul    rax, 0
0x180005d4a  mov     rcx, cs:__security_cookie
0x180005d51  mov     [rsp+rax+88h+var_20], rcx
0x180005d56  mov     eax, 8
0x180005d5b  imul    rax, 1
0x180005d5f  mov     rcx, cs:__security_cookie_complement
0x180005d66  mov     [rsp+rax+88h+var_20], rcx
0x180005d6b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180005d72  call    __raise_securityfailure
0x180005d77  nop
0x180005d78  add     rsp, 88h
0x180005d7f  retn
```
