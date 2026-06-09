# __report_gsfailure

- ea: `0x180001d30`
- end: `0x180001ed0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004f20`

## callees

- `0x180001cf4`
- `0x180001d30`

## import_xrefs

- `KERNEL32!RtlCaptureContext` at `0x180001d70`
- `KERNEL32!RtlCaptureContext` at `0x180001d70`
- `KERNEL32!RtlLookupFunctionEntry` at `0x180001d8f`
- `KERNEL32!RtlLookupFunctionEntry` at `0x180001d8f`
- `KERNEL32!RtlVirtualUnwind` at `0x180001ddc`
- `KERNEL32!RtlVirtualUnwind` at `0x180001ddc`

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
  qword_18000A180 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000A170 = -1073740791;
  dword_18000A174 = 1;
  dword_18000A188 = 3;
  qword_18000A190[0] = 2;
  qword_18000A190[1] = _security_cookie;
  qword_18000A190[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001d30  mov     [rsp+arg_0], rcx
0x180001d35  sub     rsp, 88h
0x180001d3c  mov     [rsp+88h+ControlPc], 0
0x180001d45  mov     [rsp+88h+var_30], 0
0x180001d4e  mov     [rsp+88h+FunctionEntry], 0
0x180001d57  mov     [rsp+88h+var_28], 0
0x180001d60  mov     [rsp+88h+ImageBase], 0
0x180001d69  lea     rcx, ContextRecord; ContextRecord
0x180001d70  call    cs:__imp_RtlCaptureContext
0x180001d76  mov     rax, cs:ContextRecord.Rip
0x180001d7d  mov     [rsp+88h+ControlPc], rax
0x180001d82  xor     r8d, r8d; HistoryTable
0x180001d85  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x180001d8a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x180001d8f  call    cs:__imp_RtlLookupFunctionEntry
0x180001d95  mov     [rsp+88h+FunctionEntry], rax
0x180001d9a  cmp     [rsp+88h+FunctionEntry], 0
0x180001da0  jz      short loc_180001DE5
0x180001da2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x180001dab  lea     rax, [rsp+88h+var_30]
0x180001db0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001db5  lea     rax, [rsp+88h+var_28]
0x180001dba  mov     [rsp+88h+HandlerData], rax; HandlerData
0x180001dbf  lea     rax, ContextRecord
0x180001dc6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x180001dcb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001dd0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001dd5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x180001dda  xor     ecx, ecx; HandlerType
0x180001ddc  call    cs:__imp_RtlVirtualUnwind
0x180001de2  nop
0x180001de3  jmp     short loc_180001E08
0x180001de5  mov     rax, cs:ContextRecord.Rsp
0x180001dec  mov     rax, [rax]
0x180001def  mov     cs:ContextRecord.Rip, rax
0x180001df6  mov     rax, cs:ContextRecord.Rsp
0x180001dfd  add     rax, 8
0x180001e01  mov     cs:ContextRecord.Rsp, rax
0x180001e08  mov     rax, cs:ContextRecord.Rip
0x180001e0f  mov     cs:qword_18000A180, rax
0x180001e16  mov     rax, [rsp+88h+arg_0]
0x180001e1e  mov     cs:ContextRecord.Rcx, rax
0x180001e25  mov     cs:dword_18000A170, 0C0000409h
0x180001e2f  mov     cs:dword_18000A174, 1
0x180001e39  mov     cs:dword_18000A188, 3
0x180001e43  mov     eax, 8
0x180001e48  imul    rax, 0
0x180001e4c  lea     rcx, qword_18000A190
0x180001e53  mov     qword ptr [rcx+rax], 2
0x180001e5b  mov     eax, 8
0x180001e60  imul    rax, 1
0x180001e64  lea     rcx, qword_18000A190
0x180001e6b  mov     rdx, cs:__security_cookie
0x180001e72  mov     [rcx+rax], rdx
0x180001e76  mov     eax, 8
0x180001e7b  imul    rax, 2
0x180001e7f  lea     rcx, qword_18000A190
0x180001e86  mov     rdx, cs:__security_cookie_complement
0x180001e8d  mov     [rcx+rax], rdx
0x180001e91  mov     eax, 8
0x180001e96  imul    rax, 0
0x180001e9a  mov     rcx, cs:__security_cookie
0x180001ea1  mov     [rsp+rax+88h+var_20], rcx
0x180001ea6  mov     eax, 8
0x180001eab  imul    rax, 1
0x180001eaf  mov     rcx, cs:__security_cookie_complement
0x180001eb6  mov     [rsp+rax+88h+var_20], rcx
0x180001ebb  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001ec2  call    __raise_securityfailure
0x180001ec7  nop
0x180001ec8  add     rsp, 88h
0x180001ecf  retn
```
