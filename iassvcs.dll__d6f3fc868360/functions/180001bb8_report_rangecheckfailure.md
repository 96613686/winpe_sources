# __report_rangecheckfailure

- ea: `0x180001bb8`
- end: `0x180001cde`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: `void __noreturn()`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f024`
- `0x18001217c`
- `0x18001249c`

## callees

- `0x1800019d4`
- `0x180001bb8`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x180001bf0`
- `ntdll!RtlCaptureContext` at `0x180001bf0`
- `ntdll!RtlLookupFunctionEntry` at `0x180001c0f`
- `ntdll!RtlLookupFunctionEntry` at `0x180001c0f`
- `ntdll!RtlVirtualUnwind` at `0x180001c5c`
- `ntdll!RtlVirtualUnwind` at `0x180001c5c`

## pseudocode

```c
void __noreturn _report_rangecheckfailure()
{
  struct _RUNTIME_FUNCTION *FunctionEntry; // [rsp+40h] [rbp-38h]
  DWORD64 ControlPc; // [rsp+48h] [rbp-30h]
  unsigned __int64 ImageBase; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+58h] [rbp-20h] BYREF
  PVOID HandlerData; // [rsp+60h] [rbp-18h] BYREF

  EstablisherFrame = 0;
  HandlerData = 0;
  ImageBase = 0;
  RtlCaptureContext(&ContextRecord);
  ControlPc = ContextRecord.Rip;
  FunctionEntry = RtlLookupFunctionEntry(ContextRecord.Rip, &ImageBase, 0);
  if ( FunctionEntry )
  {
    RtlVirtualUnwind(0, ImageBase, ControlPc, FunctionEntry, &ContextRecord, &HandlerData, &EstablisherFrame, 0);
  }
  else
  {
    ContextRecord.Rip = *(_QWORD *)ContextRecord.Rsp;
    ContextRecord.Rsp += 8LL;
  }
  qword_1800248A0 = ContextRecord.Rip;
  dword_180024890 = -1073740791;
  dword_180024894 = 1;
  dword_1800248A8 = 1;
  qword_1800248B0[0] = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001bb8  sub     rsp, 78h
0x180001bbc  mov     [rsp+78h+ControlPc], 0
0x180001bc5  mov     [rsp+78h+var_20], 0
0x180001bce  mov     [rsp+78h+FunctionEntry], 0
0x180001bd7  mov     [rsp+78h+var_18], 0
0x180001be0  mov     [rsp+78h+ImageBase], 0
0x180001be9  lea     rcx, ContextRecord; ContextRecord
0x180001bf0  call    cs:__imp_RtlCaptureContext
0x180001bf6  mov     rax, cs:ContextRecord.Rip
0x180001bfd  mov     [rsp+78h+ControlPc], rax
0x180001c02  xor     r8d, r8d; HistoryTable
0x180001c05  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x180001c0a  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x180001c0f  call    cs:__imp_RtlLookupFunctionEntry
0x180001c15  mov     [rsp+78h+FunctionEntry], rax
0x180001c1a  cmp     [rsp+78h+FunctionEntry], 0
0x180001c20  jz      short loc_180001C65
0x180001c22  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x180001c2b  lea     rax, [rsp+78h+var_20]
0x180001c30  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x180001c35  lea     rax, [rsp+78h+var_18]
0x180001c3a  mov     [rsp+78h+HandlerData], rax; HandlerData
0x180001c3f  lea     rax, ContextRecord
0x180001c46  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x180001c4b  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x180001c50  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x180001c55  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x180001c5a  xor     ecx, ecx; HandlerType
0x180001c5c  call    cs:__imp_RtlVirtualUnwind
0x180001c62  nop
0x180001c63  jmp     short loc_180001C88
0x180001c65  mov     rax, cs:ContextRecord.Rsp
0x180001c6c  mov     rax, [rax]
0x180001c6f  mov     cs:ContextRecord.Rip, rax
0x180001c76  mov     rax, cs:ContextRecord.Rsp
0x180001c7d  add     rax, 8
0x180001c81  mov     cs:ContextRecord.Rsp, rax
0x180001c88  mov     rax, cs:ContextRecord.Rip
0x180001c8f  mov     cs:qword_1800248A0, rax
0x180001c96  mov     cs:dword_180024890, 0C0000409h
0x180001ca0  mov     cs:dword_180024894, 1
0x180001caa  mov     cs:dword_1800248A8, 1
0x180001cb4  mov     eax, 8
0x180001cb9  imul    rax, 0
0x180001cbd  lea     rcx, qword_1800248B0
0x180001cc4  mov     qword ptr [rcx+rax], 8
0x180001ccc  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001cd3  call    __raise_securityfailure
0x180001cd8  nop
0x180001cd9  add     rsp, 78h
0x180001cdd  retn
```
