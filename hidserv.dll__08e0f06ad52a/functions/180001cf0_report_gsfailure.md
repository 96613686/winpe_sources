# __report_gsfailure

- ea: `0x180001cf0`
- end: `0x180001e90`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008450`

## callees

- `0x180001cb0`
- `0x180001cf0`

## import_xrefs

- `ntdll!RtlLookupFunctionEntry` at `0x180001d4f`
- `ntdll!RtlLookupFunctionEntry` at `0x180001d4f`
- `ntdll!RtlCaptureContext` at `0x180001d30`
- `ntdll!RtlCaptureContext` at `0x180001d30`
- `ntdll!RtlVirtualUnwind` at `0x180001d9c`
- `ntdll!RtlVirtualUnwind` at `0x180001d9c`

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
  qword_18000D180 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000D170 = -1073740791;
  dword_18000D174 = 1;
  dword_18000D188 = 3;
  qword_18000D190[0] = 2;
  qword_18000D190[1] = _security_cookie;
  qword_18000D190[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001cf0  mov     [rsp+arg_0], rcx
0x180001cf5  sub     rsp, 88h
0x180001cfc  mov     [rsp+88h+ControlPc], 0
0x180001d05  mov     [rsp+88h+var_30], 0
0x180001d0e  mov     [rsp+88h+FunctionEntry], 0
0x180001d17  mov     [rsp+88h+var_28], 0
0x180001d20  mov     [rsp+88h+ImageBase], 0
0x180001d29  lea     rcx, ContextRecord; ContextRecord
0x180001d30  call    cs:__imp_RtlCaptureContext
0x180001d36  mov     rax, cs:ContextRecord.Rip
0x180001d3d  mov     [rsp+88h+ControlPc], rax
0x180001d42  xor     r8d, r8d; HistoryTable
0x180001d45  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x180001d4a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x180001d4f  call    cs:__imp_RtlLookupFunctionEntry
0x180001d55  mov     [rsp+88h+FunctionEntry], rax
0x180001d5a  cmp     [rsp+88h+FunctionEntry], 0
0x180001d60  jz      short loc_180001DA5
0x180001d62  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x180001d6b  lea     rax, [rsp+88h+var_30]
0x180001d70  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001d75  lea     rax, [rsp+88h+var_28]
0x180001d7a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x180001d7f  lea     rax, ContextRecord
0x180001d86  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x180001d8b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001d90  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001d95  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x180001d9a  xor     ecx, ecx; HandlerType
0x180001d9c  call    cs:__imp_RtlVirtualUnwind
0x180001da2  nop
0x180001da3  jmp     short loc_180001DC8
0x180001da5  mov     rax, cs:ContextRecord.Rsp
0x180001dac  mov     rax, [rax]
0x180001daf  mov     cs:ContextRecord.Rip, rax
0x180001db6  mov     rax, cs:ContextRecord.Rsp
0x180001dbd  add     rax, 8
0x180001dc1  mov     cs:ContextRecord.Rsp, rax
0x180001dc8  mov     rax, cs:ContextRecord.Rip
0x180001dcf  mov     cs:qword_18000D180, rax
0x180001dd6  mov     rax, [rsp+88h+arg_0]
0x180001dde  mov     cs:ContextRecord.Rcx, rax
0x180001de5  mov     cs:dword_18000D170, 0C0000409h
0x180001def  mov     cs:dword_18000D174, 1
0x180001df9  mov     cs:dword_18000D188, 3
0x180001e03  mov     eax, 8
0x180001e08  imul    rax, 0
0x180001e0c  lea     rcx, qword_18000D190
0x180001e13  mov     qword ptr [rcx+rax], 2
0x180001e1b  mov     eax, 8
0x180001e20  imul    rax, 1
0x180001e24  lea     rcx, qword_18000D190
0x180001e2b  mov     rdx, cs:__security_cookie
0x180001e32  mov     [rcx+rax], rdx
0x180001e36  mov     eax, 8
0x180001e3b  imul    rax, 2
0x180001e3f  lea     rcx, qword_18000D190
0x180001e46  mov     rdx, cs:__security_cookie_complement
0x180001e4d  mov     [rcx+rax], rdx
0x180001e51  mov     eax, 8
0x180001e56  imul    rax, 0
0x180001e5a  mov     rcx, cs:__security_cookie
0x180001e61  mov     [rsp+rax+88h+var_20], rcx
0x180001e66  mov     eax, 8
0x180001e6b  imul    rax, 1
0x180001e6f  mov     rcx, cs:__security_cookie_complement
0x180001e76  mov     [rsp+rax+88h+var_20], rcx
0x180001e7b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001e82  call    __raise_securityfailure
0x180001e87  nop
0x180001e88  add     rsp, 88h
0x180001e8f  retn
```
