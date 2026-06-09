# __report_gsfailure

- ea: `0x180001880`
- end: `0x180001a20`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003100`

## callees

- `0x18000183c`
- `0x180001880`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1800018df`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1800018df`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000192c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000192c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800018c0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800018c0`

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
  unk_1800070D0 = 2;
  unk_1800070D8 = _security_cookie;
  unk_1800070E0 = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001880  mov     [rsp+arg_0], rcx
0x180001885  sub     rsp, 88h
0x18000188c  mov     [rsp+88h+ControlPc], 0
0x180001895  mov     [rsp+88h+var_30], 0
0x18000189e  mov     [rsp+88h+FunctionEntry], 0
0x1800018a7  mov     [rsp+88h+var_28], 0
0x1800018b0  mov     [rsp+88h+ImageBase], 0
0x1800018b9  lea     rcx, ContextRecord; ContextRecord
0x1800018c0  call    cs:__imp_RtlCaptureContext
0x1800018c6  mov     rax, cs:ContextRecord.Rip
0x1800018cd  mov     [rsp+88h+ControlPc], rax
0x1800018d2  xor     r8d, r8d; HistoryTable
0x1800018d5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800018da  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1800018df  call    cs:__imp_RtlLookupFunctionEntry
0x1800018e5  mov     [rsp+88h+FunctionEntry], rax
0x1800018ea  cmp     [rsp+88h+FunctionEntry], 0
0x1800018f0  jz      short loc_180001935
0x1800018f2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1800018fb  lea     rax, [rsp+88h+var_30]
0x180001900  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001905  lea     rax, [rsp+88h+var_28]
0x18000190a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000190f  lea     rax, ContextRecord
0x180001916  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000191b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001920  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001925  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000192a  xor     ecx, ecx; HandlerType
0x18000192c  call    cs:__imp_RtlVirtualUnwind
0x180001932  nop
0x180001933  jmp     short loc_180001958
0x180001935  mov     rax, cs:ContextRecord.Rsp
0x18000193c  mov     rax, [rax]
0x18000193f  mov     cs:ContextRecord.Rip, rax
0x180001946  mov     rax, cs:ContextRecord.Rsp
0x18000194d  add     rax, 8
0x180001951  mov     cs:ContextRecord.Rsp, rax
0x180001958  mov     rax, cs:ContextRecord.Rip
0x18000195f  mov     cs:qword_1800070C0, rax
0x180001966  mov     rax, [rsp+88h+arg_0]
0x18000196e  mov     cs:ContextRecord.Rcx, rax
0x180001975  mov     cs:dword_1800070B0, 0C0000409h
0x18000197f  mov     cs:dword_1800070B4, 1
0x180001989  mov     cs:dword_1800070C8, 3
0x180001993  mov     eax, 8
0x180001998  imul    rax, 0
0x18000199c  lea     rcx, unk_1800070D0
0x1800019a3  mov     qword ptr [rcx+rax], 2
0x1800019ab  mov     eax, 8
0x1800019b0  imul    rax, 1
0x1800019b4  lea     rcx, unk_1800070D0
0x1800019bb  mov     rdx, cs:__security_cookie
0x1800019c2  mov     [rcx+rax], rdx
0x1800019c6  mov     eax, 8
0x1800019cb  imul    rax, 2
0x1800019cf  lea     rcx, unk_1800070D0
0x1800019d6  mov     rdx, cs:__security_cookie_complement
0x1800019dd  mov     [rcx+rax], rdx
0x1800019e1  mov     eax, 8
0x1800019e6  imul    rax, 0
0x1800019ea  mov     rcx, cs:__security_cookie
0x1800019f1  mov     [rsp+rax+88h+var_20], rcx
0x1800019f6  mov     eax, 8
0x1800019fb  imul    rax, 1
0x1800019ff  mov     rcx, cs:__security_cookie_complement
0x180001a06  mov     [rsp+rax+88h+var_20], rcx
0x180001a0b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001a12  call    __raise_securityfailure
0x180001a17  nop
0x180001a18  add     rsp, 88h
0x180001a1f  retn
```
