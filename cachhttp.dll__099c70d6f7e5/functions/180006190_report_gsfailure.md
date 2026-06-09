# __report_gsfailure

- ea: `0x180006190`
- end: `0x180006330`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008bf0`

## callees

- `0x18000614c`
- `0x180006190`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x1800061d0`
- `ntdll!RtlCaptureContext` at `0x1800061d0`
- `ntdll!RtlLookupFunctionEntry` at `0x1800061ef`
- `ntdll!RtlLookupFunctionEntry` at `0x1800061ef`
- `ntdll!RtlVirtualUnwind` at `0x18000623c`
- `ntdll!RtlVirtualUnwind` at `0x18000623c`

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
  qword_18000E0C0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000E0B0 = -1073740791;
  dword_18000E0B4 = 1;
  dword_18000E0C8 = 3;
  qword_18000E0D0[0] = 2;
  qword_18000E0D0[1] = _security_cookie;
  qword_18000E0D0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180006190  mov     [rsp+arg_0], rcx
0x180006195  sub     rsp, 88h
0x18000619c  mov     [rsp+88h+ControlPc], 0
0x1800061a5  mov     [rsp+88h+var_30], 0
0x1800061ae  mov     [rsp+88h+FunctionEntry], 0
0x1800061b7  mov     [rsp+88h+var_28], 0
0x1800061c0  mov     [rsp+88h+ImageBase], 0
0x1800061c9  lea     rcx, ContextRecord; ContextRecord
0x1800061d0  call    cs:__imp_RtlCaptureContext
0x1800061d6  mov     rax, cs:ContextRecord.Rip
0x1800061dd  mov     [rsp+88h+ControlPc], rax
0x1800061e2  xor     r8d, r8d; HistoryTable
0x1800061e5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800061ea  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1800061ef  call    cs:__imp_RtlLookupFunctionEntry
0x1800061f5  mov     [rsp+88h+FunctionEntry], rax
0x1800061fa  cmp     [rsp+88h+FunctionEntry], 0
0x180006200  jz      short loc_180006245
0x180006202  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000620b  lea     rax, [rsp+88h+var_30]
0x180006210  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180006215  lea     rax, [rsp+88h+var_28]
0x18000621a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000621f  lea     rax, ContextRecord
0x180006226  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000622b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180006230  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180006235  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000623a  xor     ecx, ecx; HandlerType
0x18000623c  call    cs:__imp_RtlVirtualUnwind
0x180006242  nop
0x180006243  jmp     short loc_180006268
0x180006245  mov     rax, cs:ContextRecord.Rsp
0x18000624c  mov     rax, [rax]
0x18000624f  mov     cs:ContextRecord.Rip, rax
0x180006256  mov     rax, cs:ContextRecord.Rsp
0x18000625d  add     rax, 8
0x180006261  mov     cs:ContextRecord.Rsp, rax
0x180006268  mov     rax, cs:ContextRecord.Rip
0x18000626f  mov     cs:qword_18000E0C0, rax
0x180006276  mov     rax, [rsp+88h+arg_0]
0x18000627e  mov     cs:ContextRecord.Rcx, rax
0x180006285  mov     cs:dword_18000E0B0, 0C0000409h
0x18000628f  mov     cs:dword_18000E0B4, 1
0x180006299  mov     cs:dword_18000E0C8, 3
0x1800062a3  mov     eax, 8
0x1800062a8  imul    rax, 0
0x1800062ac  lea     rcx, qword_18000E0D0
0x1800062b3  mov     qword ptr [rcx+rax], 2
0x1800062bb  mov     eax, 8
0x1800062c0  imul    rax, 1
0x1800062c4  lea     rcx, qword_18000E0D0
0x1800062cb  mov     rdx, cs:__security_cookie
0x1800062d2  mov     [rcx+rax], rdx
0x1800062d6  mov     eax, 8
0x1800062db  imul    rax, 2
0x1800062df  lea     rcx, qword_18000E0D0
0x1800062e6  mov     rdx, cs:__security_cookie_complement
0x1800062ed  mov     [rcx+rax], rdx
0x1800062f1  mov     eax, 8
0x1800062f6  imul    rax, 0
0x1800062fa  mov     rcx, cs:__security_cookie
0x180006301  mov     [rsp+rax+88h+var_20], rcx
0x180006306  mov     eax, 8
0x18000630b  imul    rax, 1
0x18000630f  mov     rcx, cs:__security_cookie_complement
0x180006316  mov     [rsp+rax+88h+var_20], rcx
0x18000631b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180006322  call    __raise_securityfailure
0x180006327  nop
0x180006328  add     rsp, 88h
0x18000632f  retn
```
