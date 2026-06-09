# __report_gsfailure

- ea: `0x180001120`
- end: `0x180001294`
- name: `__report_gsfailure`
- size: `372`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003060`

## callees

- `0x180001120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001271`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001271`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001264`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001264`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001285`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001285`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001277`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001277`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000117f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000117f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001160`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001160`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x1800011cc`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x1800011cc`

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
0x180001120  mov     [rsp+arg_0], rcx
0x180001125  sub     rsp, 88h
0x18000112c  mov     [rsp+88h+ControlPc], 0
0x180001135  mov     [rsp+88h+var_30], 0
0x18000113e  mov     [rsp+88h+FunctionEntry], 0
0x180001147  mov     [rsp+88h+var_28], 0
0x180001150  mov     [rsp+88h+ImageBase], 0
0x180001159  lea     rcx, ContextRecord; ContextRecord
0x180001160  call    cs:__imp_RtlCaptureContext
0x180001166  mov     rax, cs:ContextRecord.Rip
0x18000116d  mov     [rsp+88h+ControlPc], rax
0x180001172  xor     r8d, r8d; HistoryTable
0x180001175  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000117a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000117f  call    cs:__imp_RtlLookupFunctionEntry
0x180001185  mov     [rsp+88h+FunctionEntry], rax
0x18000118a  cmp     [rsp+88h+FunctionEntry], 0
0x180001190  jz      short loc_1800011D5
0x180001192  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000119b  lea     rax, [rsp+88h+var_30]
0x1800011a0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1800011a5  lea     rax, [rsp+88h+var_28]
0x1800011aa  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1800011af  lea     rax, ContextRecord
0x1800011b6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1800011bb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1800011c0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1800011c5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800011ca  xor     ecx, ecx; HandlerType
0x1800011cc  call    cs:__imp_RtlVirtualUnwind
0x1800011d2  nop
0x1800011d3  jmp     short loc_1800011F7
0x1800011d5  mov     rax, [rsp+88h]
0x1800011dd  mov     cs:ContextRecord.Rip, rax
0x1800011e4  lea     rax, [rsp+88h]
0x1800011ec  add     rax, 8
0x1800011f0  mov     cs:ContextRecord.Rsp, rax
0x1800011f7  mov     rax, cs:ContextRecord.Rip
0x1800011fe  mov     cs:qword_180007030, rax
0x180001205  mov     rax, [rsp+88h+arg_0]
0x18000120d  mov     cs:ContextRecord.Rcx, rax
0x180001214  mov     cs:dword_180007020, 0C0000409h
0x18000121e  mov     cs:dword_180007024, 1
0x180001228  mov     cs:dword_180007038, 1
0x180001232  mov     eax, 8
0x180001237  imul    rax, 0
0x18000123b  lea     rcx, qword_180007040
0x180001242  mov     qword ptr [rcx+rax], 2
0x18000124a  mov     rax, cs:__security_cookie
0x180001251  mov     [rsp+88h+var_20], rax
0x180001256  mov     rax, cs:__security_cookie_complement
0x18000125d  mov     [rsp+88h+var_18], rax
0x180001262  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001264  call    cs:__imp_SetUnhandledExceptionFilter
0x18000126a  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001271  call    cs:__imp_UnhandledExceptionFilter
0x180001277  call    cs:__imp_GetCurrentProcess
0x18000127d  mov     edx, 0C0000409h; uExitCode
0x180001282  mov     rcx, rax; hProcess
0x180001285  call    cs:__imp_TerminateProcess
0x18000128b  nop
0x18000128c  add     rsp, 88h
0x180001293  retn
```
