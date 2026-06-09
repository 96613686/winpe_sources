# __report_gsfailure

- ea: `0x1800026b0`
- end: `0x180002824`
- name: `__report_gsfailure`
- size: `372`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003b50`

## callees

- `0x1800026b0`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x1800026f0`
- `ntdll!RtlCaptureContext` at `0x1800026f0`
- `ntdll!RtlVirtualUnwind` at `0x18000275c`
- `ntdll!RtlVirtualUnwind` at `0x18000275c`
- `ntdll!RtlLookupFunctionEntry` at `0x18000270f`
- `ntdll!RtlLookupFunctionEntry` at `0x18000270f`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002801`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002801`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800027f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800027f4`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002815`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002815`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002807`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002807`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  HANDLE CurrentProcess; // rax
  struct _RUNTIME_FUNCTION *FunctionEntry; // [rsp+40h] [rbp-48h]
  DWORD64 ControlPc; // [rsp+48h] [rbp-40h]
  unsigned __int64 ImageBase; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+58h] [rbp-30h] BYREF
  PVOID HandlerData[5]; // [rsp+60h] [rbp-28h] BYREF
  DWORD64 retaddr; // [rsp+88h] [rbp+0h]
  uintptr_t v8; // [rsp+90h] [rbp+8h] BYREF

  v8 = StackCookie;
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
    ContextRecord.Rip = retaddr;
    ContextRecord.Rsp = (DWORD64)&v8;
  }
  qword_180007030 = ContextRecord.Rip;
  ContextRecord.Rcx = v8;
  dword_180007020 = -1073740791;
  dword_180007024 = 1;
  dword_180007038 = 1;
  qword_180007040[0] = 2;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  SetUnhandledExceptionFilter(0);
  UnhandledExceptionFilter((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
  CurrentProcess = GetCurrentProcess();
  TerminateProcess(CurrentProcess, 0xC0000409);
}

```

## disassembly

```asm
0x1800026b0  mov     [rsp+arg_0], rcx
0x1800026b5  sub     rsp, 88h
0x1800026bc  mov     [rsp+88h+ControlPc], 0
0x1800026c5  mov     [rsp+88h+var_30], 0
0x1800026ce  mov     [rsp+88h+FunctionEntry], 0
0x1800026d7  mov     [rsp+88h+var_28], 0
0x1800026e0  mov     [rsp+88h+ImageBase], 0
0x1800026e9  lea     rcx, ContextRecord; ContextRecord
0x1800026f0  call    cs:__imp_RtlCaptureContext
0x1800026f6  mov     rax, cs:ContextRecord.Rip
0x1800026fd  mov     [rsp+88h+ControlPc], rax
0x180002702  xor     r8d, r8d; HistoryTable
0x180002705  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000270a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000270f  call    cs:__imp_RtlLookupFunctionEntry
0x180002715  mov     [rsp+88h+FunctionEntry], rax
0x18000271a  cmp     [rsp+88h+FunctionEntry], 0
0x180002720  jz      short loc_180002765
0x180002722  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000272b  lea     rax, [rsp+88h+var_30]
0x180002730  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180002735  lea     rax, [rsp+88h+var_28]
0x18000273a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000273f  lea     rax, ContextRecord
0x180002746  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000274b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180002750  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180002755  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000275a  xor     ecx, ecx; HandlerType
0x18000275c  call    cs:__imp_RtlVirtualUnwind
0x180002762  nop
0x180002763  jmp     short loc_180002787
0x180002765  mov     rax, [rsp+88h]
0x18000276d  mov     cs:ContextRecord.Rip, rax
0x180002774  lea     rax, [rsp+88h]
0x18000277c  add     rax, 8
0x180002780  mov     cs:ContextRecord.Rsp, rax
0x180002787  mov     rax, cs:ContextRecord.Rip
0x18000278e  mov     cs:qword_180007030, rax
0x180002795  mov     rax, [rsp+88h+arg_0]
0x18000279d  mov     cs:ContextRecord.Rcx, rax
0x1800027a4  mov     cs:dword_180007020, 0C0000409h
0x1800027ae  mov     cs:dword_180007024, 1
0x1800027b8  mov     cs:dword_180007038, 1
0x1800027c2  mov     eax, 8
0x1800027c7  imul    rax, 0
0x1800027cb  lea     rcx, qword_180007040
0x1800027d2  mov     qword ptr [rcx+rax], 2
0x1800027da  mov     rax, cs:__security_cookie
0x1800027e1  mov     [rsp+88h+var_20], rax
0x1800027e6  mov     rax, cs:__security_cookie_complement
0x1800027ed  mov     [rsp+88h+var_18], rax
0x1800027f2  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800027f4  call    cs:__imp_SetUnhandledExceptionFilter
0x1800027fa  lea     rcx, ExceptionInfo; ExceptionInfo
0x180002801  call    cs:__imp_UnhandledExceptionFilter
0x180002807  call    cs:__imp_GetCurrentProcess
0x18000280d  mov     edx, 0C0000409h; uExitCode
0x180002812  mov     rcx, rax; hProcess
0x180002815  call    cs:__imp_TerminateProcess
0x18000281b  nop
0x18000281c  add     rsp, 88h
0x180002823  retn
```
