# __report_gsfailure

- ea: `0x180001010`
- end: `0x180001184`
- name: `__report_gsfailure`
- size: `372`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005c60`

## callees

- `0x180001010`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x180001050`
- `ntdll!RtlCaptureContext` at `0x180001050`
- `ntdll!RtlVirtualUnwind` at `0x1800010bc`
- `ntdll!RtlVirtualUnwind` at `0x1800010bc`
- `ntdll!RtlLookupFunctionEntry` at `0x18000106f`
- `ntdll!RtlLookupFunctionEntry` at `0x18000106f`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001154`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001154`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001161`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001161`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001175`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001175`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001167`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001167`

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
  qword_180008050 = ContextRecord.Rip;
  ContextRecord.Rcx = v8;
  dword_180008040 = -1073740791;
  dword_180008044 = 1;
  dword_180008058 = 1;
  unk_180008060 = 2;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  SetUnhandledExceptionFilter(0);
  UnhandledExceptionFilter((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
  CurrentProcess = GetCurrentProcess();
  TerminateProcess(CurrentProcess, 0xC0000409);
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_0], rcx
0x180001015  sub     rsp, 88h
0x18000101c  mov     [rsp+88h+ControlPc], 0
0x180001025  mov     [rsp+88h+var_30], 0
0x18000102e  mov     [rsp+88h+FunctionEntry], 0
0x180001037  mov     [rsp+88h+var_28], 0
0x180001040  mov     [rsp+88h+ImageBase], 0
0x180001049  lea     rcx, ContextRecord; ContextRecord
0x180001050  call    cs:__imp_RtlCaptureContext
0x180001056  mov     rax, cs:ContextRecord.Rip
0x18000105d  mov     [rsp+88h+ControlPc], rax
0x180001062  xor     r8d, r8d; HistoryTable
0x180001065  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000106a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000106f  call    cs:__imp_RtlLookupFunctionEntry
0x180001075  mov     [rsp+88h+FunctionEntry], rax
0x18000107a  cmp     [rsp+88h+FunctionEntry], 0
0x180001080  jz      short loc_1800010C5
0x180001082  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000108b  lea     rax, [rsp+88h+var_30]
0x180001090  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001095  lea     rax, [rsp+88h+var_28]
0x18000109a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000109f  lea     rax, ContextRecord
0x1800010a6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1800010ab  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1800010b0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1800010b5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800010ba  xor     ecx, ecx; HandlerType
0x1800010bc  call    cs:__imp_RtlVirtualUnwind
0x1800010c2  nop
0x1800010c3  jmp     short loc_1800010E7
0x1800010c5  mov     rax, [rsp+88h]
0x1800010cd  mov     cs:ContextRecord.Rip, rax
0x1800010d4  lea     rax, [rsp+88h]
0x1800010dc  add     rax, 8
0x1800010e0  mov     cs:ContextRecord.Rsp, rax
0x1800010e7  mov     rax, cs:ContextRecord.Rip
0x1800010ee  mov     cs:qword_180008050, rax
0x1800010f5  mov     rax, [rsp+88h+arg_0]
0x1800010fd  mov     cs:ContextRecord.Rcx, rax
0x180001104  mov     cs:dword_180008040, 0C0000409h
0x18000110e  mov     cs:dword_180008044, 1
0x180001118  mov     cs:dword_180008058, 1
0x180001122  mov     eax, 8
0x180001127  imul    rax, 0
0x18000112b  lea     rcx, unk_180008060
0x180001132  mov     qword ptr [rcx+rax], 2
0x18000113a  mov     rax, cs:__security_cookie
0x180001141  mov     [rsp+88h+var_20], rax
0x180001146  mov     rax, cs:__security_cookie_complement
0x18000114d  mov     [rsp+88h+var_18], rax
0x180001152  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001154  call    cs:__imp_SetUnhandledExceptionFilter
0x18000115a  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001161  call    cs:__imp_UnhandledExceptionFilter
0x180001167  call    cs:__imp_GetCurrentProcess
0x18000116d  mov     edx, 0C0000409h; uExitCode
0x180001172  mov     rcx, rax; hProcess
0x180001175  call    cs:__imp_TerminateProcess
0x18000117b  nop
0x18000117c  add     rsp, 88h
0x180001183  retn
```
