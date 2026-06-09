# __report_gsfailure

- ea: `0x180001530`
- end: `0x1800016d0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800054b0`

## callees

- `0x1800014f0`
- `0x180001530`

## import_xrefs

- `KERNEL32!RtlCaptureContext` at `0x180001570`
- `KERNEL32!RtlCaptureContext` at `0x180001570`
- `KERNEL32!RtlLookupFunctionEntry` at `0x18000158f`
- `KERNEL32!RtlLookupFunctionEntry` at `0x18000158f`
- `KERNEL32!RtlVirtualUnwind` at `0x1800015dc`
- `KERNEL32!RtlVirtualUnwind` at `0x1800015dc`

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
  qword_18000C140 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000C130 = -1073740791;
  dword_18000C134 = 1;
  dword_18000C148 = 3;
  qword_18000C150[0] = 2;
  qword_18000C150[1] = _security_cookie;
  qword_18000C150[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001530  mov     [rsp+arg_0], rcx
0x180001535  sub     rsp, 88h
0x18000153c  mov     [rsp+88h+ControlPc], 0
0x180001545  mov     [rsp+88h+var_30], 0
0x18000154e  mov     [rsp+88h+FunctionEntry], 0
0x180001557  mov     [rsp+88h+var_28], 0
0x180001560  mov     [rsp+88h+ImageBase], 0
0x180001569  lea     rcx, ContextRecord; ContextRecord
0x180001570  call    cs:__imp_RtlCaptureContext
0x180001576  mov     rax, cs:ContextRecord.Rip
0x18000157d  mov     [rsp+88h+ControlPc], rax
0x180001582  xor     r8d, r8d; HistoryTable
0x180001585  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000158a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000158f  call    cs:__imp_RtlLookupFunctionEntry
0x180001595  mov     [rsp+88h+FunctionEntry], rax
0x18000159a  cmp     [rsp+88h+FunctionEntry], 0
0x1800015a0  jz      short loc_1800015E5
0x1800015a2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1800015ab  lea     rax, [rsp+88h+var_30]
0x1800015b0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1800015b5  lea     rax, [rsp+88h+var_28]
0x1800015ba  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1800015bf  lea     rax, ContextRecord
0x1800015c6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1800015cb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1800015d0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1800015d5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800015da  xor     ecx, ecx; HandlerType
0x1800015dc  call    cs:__imp_RtlVirtualUnwind
0x1800015e2  nop
0x1800015e3  jmp     short loc_180001608
0x1800015e5  mov     rax, cs:ContextRecord.Rsp
0x1800015ec  mov     rax, [rax]
0x1800015ef  mov     cs:ContextRecord.Rip, rax
0x1800015f6  mov     rax, cs:ContextRecord.Rsp
0x1800015fd  add     rax, 8
0x180001601  mov     cs:ContextRecord.Rsp, rax
0x180001608  mov     rax, cs:ContextRecord.Rip
0x18000160f  mov     cs:qword_18000C140, rax
0x180001616  mov     rax, [rsp+88h+arg_0]
0x18000161e  mov     cs:ContextRecord.Rcx, rax
0x180001625  mov     cs:dword_18000C130, 0C0000409h
0x18000162f  mov     cs:dword_18000C134, 1
0x180001639  mov     cs:dword_18000C148, 3
0x180001643  mov     eax, 8
0x180001648  imul    rax, 0
0x18000164c  lea     rcx, qword_18000C150
0x180001653  mov     qword ptr [rcx+rax], 2
0x18000165b  mov     eax, 8
0x180001660  imul    rax, 1
0x180001664  lea     rcx, qword_18000C150
0x18000166b  mov     rdx, cs:__security_cookie
0x180001672  mov     [rcx+rax], rdx
0x180001676  mov     eax, 8
0x18000167b  imul    rax, 2
0x18000167f  lea     rcx, qword_18000C150
0x180001686  mov     rdx, cs:__security_cookie_complement
0x18000168d  mov     [rcx+rax], rdx
0x180001691  mov     eax, 8
0x180001696  imul    rax, 0
0x18000169a  mov     rcx, cs:__security_cookie
0x1800016a1  mov     [rsp+rax+88h+var_20], rcx
0x1800016a6  mov     eax, 8
0x1800016ab  imul    rax, 1
0x1800016af  mov     rcx, cs:__security_cookie_complement
0x1800016b6  mov     [rsp+rax+88h+var_20], rcx
0x1800016bb  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800016c2  call    __raise_securityfailure
0x1800016c7  nop
0x1800016c8  add     rsp, 88h
0x1800016cf  retn
```
