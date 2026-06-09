# __report_gsfailure

- ea: `0x180002de0`
- end: `0x180002f80`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005720`

## callees

- `0x180002da0`
- `0x180002de0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180002e3f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180002e3f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x180002e8c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x180002e8c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180002e20`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180002e20`

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
  qword_18000B160 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000B150 = -1073740791;
  dword_18000B154 = 1;
  dword_18000B168 = 3;
  qword_18000B170[0] = 2;
  qword_18000B170[1] = _security_cookie;
  qword_18000B170[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180002de0  mov     [rsp+arg_0], rcx
0x180002de5  sub     rsp, 88h
0x180002dec  mov     [rsp+88h+ControlPc], 0
0x180002df5  mov     [rsp+88h+var_30], 0
0x180002dfe  mov     [rsp+88h+FunctionEntry], 0
0x180002e07  mov     [rsp+88h+var_28], 0
0x180002e10  mov     [rsp+88h+ImageBase], 0
0x180002e19  lea     rcx, ContextRecord; ContextRecord
0x180002e20  call    cs:__imp_RtlCaptureContext
0x180002e26  mov     rax, cs:ContextRecord.Rip
0x180002e2d  mov     [rsp+88h+ControlPc], rax
0x180002e32  xor     r8d, r8d; HistoryTable
0x180002e35  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x180002e3a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x180002e3f  call    cs:__imp_RtlLookupFunctionEntry
0x180002e45  mov     [rsp+88h+FunctionEntry], rax
0x180002e4a  cmp     [rsp+88h+FunctionEntry], 0
0x180002e50  jz      short loc_180002E95
0x180002e52  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x180002e5b  lea     rax, [rsp+88h+var_30]
0x180002e60  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180002e65  lea     rax, [rsp+88h+var_28]
0x180002e6a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x180002e6f  lea     rax, ContextRecord
0x180002e76  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x180002e7b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180002e80  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180002e85  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x180002e8a  xor     ecx, ecx; HandlerType
0x180002e8c  call    cs:__imp_RtlVirtualUnwind
0x180002e92  nop
0x180002e93  jmp     short loc_180002EB8
0x180002e95  mov     rax, cs:ContextRecord.Rsp
0x180002e9c  mov     rax, [rax]
0x180002e9f  mov     cs:ContextRecord.Rip, rax
0x180002ea6  mov     rax, cs:ContextRecord.Rsp
0x180002ead  add     rax, 8
0x180002eb1  mov     cs:ContextRecord.Rsp, rax
0x180002eb8  mov     rax, cs:ContextRecord.Rip
0x180002ebf  mov     cs:qword_18000B160, rax
0x180002ec6  mov     rax, [rsp+88h+arg_0]
0x180002ece  mov     cs:ContextRecord.Rcx, rax
0x180002ed5  mov     cs:dword_18000B150, 0C0000409h
0x180002edf  mov     cs:dword_18000B154, 1
0x180002ee9  mov     cs:dword_18000B168, 3
0x180002ef3  mov     eax, 8
0x180002ef8  imul    rax, 0
0x180002efc  lea     rcx, qword_18000B170
0x180002f03  mov     qword ptr [rcx+rax], 2
0x180002f0b  mov     eax, 8
0x180002f10  imul    rax, 1
0x180002f14  lea     rcx, qword_18000B170
0x180002f1b  mov     rdx, cs:__security_cookie
0x180002f22  mov     [rcx+rax], rdx
0x180002f26  mov     eax, 8
0x180002f2b  imul    rax, 2
0x180002f2f  lea     rcx, qword_18000B170
0x180002f36  mov     rdx, cs:__security_cookie_complement
0x180002f3d  mov     [rcx+rax], rdx
0x180002f41  mov     eax, 8
0x180002f46  imul    rax, 0
0x180002f4a  mov     rcx, cs:__security_cookie
0x180002f51  mov     [rsp+rax+88h+var_20], rcx
0x180002f56  mov     eax, 8
0x180002f5b  imul    rax, 1
0x180002f5f  mov     rcx, cs:__security_cookie_complement
0x180002f66  mov     [rsp+rax+88h+var_20], rcx
0x180002f6b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180002f72  call    __raise_securityfailure
0x180002f77  nop
0x180002f78  add     rsp, 88h
0x180002f7f  retn
```
