# __report_gsfailure

- ea: `0x180003060`
- end: `0x180003200`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003c70`

## callees

- `0x18000301c`
- `0x180003060`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x1800030a0`
- `ntdll!RtlCaptureContext` at `0x1800030a0`
- `ntdll!RtlLookupFunctionEntry` at `0x1800030bf`
- `ntdll!RtlLookupFunctionEntry` at `0x1800030bf`
- `ntdll!RtlVirtualUnwind` at `0x18000310c`
- `ntdll!RtlVirtualUnwind` at `0x18000310c`

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
  qword_1800080C0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_1800080B0 = -1073740791;
  dword_1800080B4 = 1;
  dword_1800080C8 = 3;
  qword_1800080D0[0] = 2;
  qword_1800080D0[1] = _security_cookie;
  qword_1800080D0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180003060  mov     [rsp+arg_0], rcx
0x180003065  sub     rsp, 88h
0x18000306c  mov     [rsp+88h+ControlPc], 0
0x180003075  mov     [rsp+88h+var_30], 0
0x18000307e  mov     [rsp+88h+FunctionEntry], 0
0x180003087  mov     [rsp+88h+var_28], 0
0x180003090  mov     [rsp+88h+ImageBase], 0
0x180003099  lea     rcx, ContextRecord; ContextRecord
0x1800030a0  call    cs:__imp_RtlCaptureContext
0x1800030a6  mov     rax, cs:ContextRecord.Rip
0x1800030ad  mov     [rsp+88h+ControlPc], rax
0x1800030b2  xor     r8d, r8d; HistoryTable
0x1800030b5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800030ba  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1800030bf  call    cs:__imp_RtlLookupFunctionEntry
0x1800030c5  mov     [rsp+88h+FunctionEntry], rax
0x1800030ca  cmp     [rsp+88h+FunctionEntry], 0
0x1800030d0  jz      short loc_180003115
0x1800030d2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1800030db  lea     rax, [rsp+88h+var_30]
0x1800030e0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1800030e5  lea     rax, [rsp+88h+var_28]
0x1800030ea  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1800030ef  lea     rax, ContextRecord
0x1800030f6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1800030fb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180003100  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180003105  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000310a  xor     ecx, ecx; HandlerType
0x18000310c  call    cs:__imp_RtlVirtualUnwind
0x180003112  nop
0x180003113  jmp     short loc_180003138
0x180003115  mov     rax, cs:ContextRecord.Rsp
0x18000311c  mov     rax, [rax]
0x18000311f  mov     cs:ContextRecord.Rip, rax
0x180003126  mov     rax, cs:ContextRecord.Rsp
0x18000312d  add     rax, 8
0x180003131  mov     cs:ContextRecord.Rsp, rax
0x180003138  mov     rax, cs:ContextRecord.Rip
0x18000313f  mov     cs:qword_1800080C0, rax
0x180003146  mov     rax, [rsp+88h+arg_0]
0x18000314e  mov     cs:ContextRecord.Rcx, rax
0x180003155  mov     cs:dword_1800080B0, 0C0000409h
0x18000315f  mov     cs:dword_1800080B4, 1
0x180003169  mov     cs:dword_1800080C8, 3
0x180003173  mov     eax, 8
0x180003178  imul    rax, 0
0x18000317c  lea     rcx, qword_1800080D0
0x180003183  mov     qword ptr [rcx+rax], 2
0x18000318b  mov     eax, 8
0x180003190  imul    rax, 1
0x180003194  lea     rcx, qword_1800080D0
0x18000319b  mov     rdx, cs:__security_cookie
0x1800031a2  mov     [rcx+rax], rdx
0x1800031a6  mov     eax, 8
0x1800031ab  imul    rax, 2
0x1800031af  lea     rcx, qword_1800080D0
0x1800031b6  mov     rdx, cs:__security_cookie_complement
0x1800031bd  mov     [rcx+rax], rdx
0x1800031c1  mov     eax, 8
0x1800031c6  imul    rax, 0
0x1800031ca  mov     rcx, cs:__security_cookie
0x1800031d1  mov     [rsp+rax+88h+var_20], rcx
0x1800031d6  mov     eax, 8
0x1800031db  imul    rax, 1
0x1800031df  mov     rcx, cs:__security_cookie_complement
0x1800031e6  mov     [rsp+rax+88h+var_20], rcx
0x1800031eb  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800031f2  call    __raise_securityfailure
0x1800031f7  nop
0x1800031f8  add     rsp, 88h
0x1800031ff  retn
```
