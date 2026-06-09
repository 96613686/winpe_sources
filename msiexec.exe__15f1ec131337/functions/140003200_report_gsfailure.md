# __report_gsfailure

- ea: `0x140003200`
- end: `0x1400033a0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009820`

## callees

- `0x1400031b8`
- `0x140003200`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x140003240`
- `ntdll!RtlCaptureContext` at `0x140003240`
- `ntdll!RtlLookupFunctionEntry` at `0x14000325f`
- `ntdll!RtlLookupFunctionEntry` at `0x14000325f`
- `ntdll!RtlVirtualUnwind` at `0x1400032ac`
- `ntdll!RtlVirtualUnwind` at `0x1400032ac`

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
  qword_140010200 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_1400101F0 = -1073740791;
  dword_1400101F4 = 1;
  dword_140010208 = 3;
  qword_140010210[0] = 2;
  qword_140010210[1] = _security_cookie;
  qword_140010210[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x140003200  mov     [rsp+arg_0], rcx
0x140003205  sub     rsp, 88h
0x14000320c  mov     [rsp+88h+ControlPc], 0
0x140003215  mov     [rsp+88h+var_30], 0
0x14000321e  mov     [rsp+88h+FunctionEntry], 0
0x140003227  mov     [rsp+88h+var_28], 0
0x140003230  mov     [rsp+88h+ImageBase], 0
0x140003239  lea     rcx, ContextRecord; ContextRecord
0x140003240  call    cs:__imp_RtlCaptureContext
0x140003246  mov     rax, cs:ContextRecord.Rip
0x14000324d  mov     [rsp+88h+ControlPc], rax
0x140003252  xor     r8d, r8d; HistoryTable
0x140003255  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x14000325a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x14000325f  call    cs:__imp_RtlLookupFunctionEntry
0x140003265  mov     [rsp+88h+FunctionEntry], rax
0x14000326a  cmp     [rsp+88h+FunctionEntry], 0
0x140003270  jz      short loc_1400032B5
0x140003272  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x14000327b  lea     rax, [rsp+88h+var_30]
0x140003280  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x140003285  lea     rax, [rsp+88h+var_28]
0x14000328a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x14000328f  lea     rax, ContextRecord
0x140003296  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x14000329b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1400032a0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1400032a5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1400032aa  xor     ecx, ecx; HandlerType
0x1400032ac  call    cs:__imp_RtlVirtualUnwind
0x1400032b2  nop
0x1400032b3  jmp     short loc_1400032D8
0x1400032b5  mov     rax, cs:ContextRecord.Rsp
0x1400032bc  mov     rax, [rax]
0x1400032bf  mov     cs:ContextRecord.Rip, rax
0x1400032c6  mov     rax, cs:ContextRecord.Rsp
0x1400032cd  add     rax, 8
0x1400032d1  mov     cs:ContextRecord.Rsp, rax
0x1400032d8  mov     rax, cs:ContextRecord.Rip
0x1400032df  mov     cs:qword_140010200, rax
0x1400032e6  mov     rax, [rsp+88h+arg_0]
0x1400032ee  mov     cs:ContextRecord.Rcx, rax
0x1400032f5  mov     cs:dword_1400101F0, 0C0000409h
0x1400032ff  mov     cs:dword_1400101F4, 1
0x140003309  mov     cs:dword_140010208, 3
0x140003313  mov     eax, 8
0x140003318  imul    rax, 0
0x14000331c  lea     rcx, qword_140010210
0x140003323  mov     qword ptr [rcx+rax], 2
0x14000332b  mov     eax, 8
0x140003330  imul    rax, 1
0x140003334  lea     rcx, qword_140010210
0x14000333b  mov     rdx, cs:__security_cookie
0x140003342  mov     [rcx+rax], rdx
0x140003346  mov     eax, 8
0x14000334b  imul    rax, 2
0x14000334f  lea     rcx, qword_140010210
0x140003356  mov     rdx, cs:__security_cookie_complement
0x14000335d  mov     [rcx+rax], rdx
0x140003361  mov     eax, 8
0x140003366  imul    rax, 0
0x14000336a  mov     rcx, cs:__security_cookie
0x140003371  mov     [rsp+rax+88h+var_20], rcx
0x140003376  mov     eax, 8
0x14000337b  imul    rax, 1
0x14000337f  mov     rcx, cs:__security_cookie_complement
0x140003386  mov     [rsp+rax+88h+var_20], rcx
0x14000338b  lea     rcx, ExceptionInfo; ExceptionInfo
0x140003392  call    __raise_securityfailure
0x140003397  nop
0x140003398  add     rsp, 88h
0x14000339f  retn
```
