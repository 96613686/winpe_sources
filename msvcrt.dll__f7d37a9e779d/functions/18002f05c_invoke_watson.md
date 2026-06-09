# _invoke_watson

- ea: `0x18002f05c`
- end: `0x18002f141`
- name: `_invoke_watson`
- size: `229`
- prototype: `void __cdecl __noreturn(const wchar_t *Expression, const wchar_t *FunctionName, const wchar_t *FileName, unsigned int LineNo, uintptr_t Reserved)`
- caller_count: `96`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006c90`
- `0x180006e00`
- `0x1800070b0`
- `0x180007220`
- `0x180007454`
- `0x1800075b4`
- `0x180007718`
- `0x180007878`
- `0x180018cc0`
- `0x180019010`
- `0x180019810`
- `0x180019b70`
- `0x18001a300`
- `0x18001a660`
- `0x18001ad60`
- `0x18001b0e0`
- `0x18001b370`
- `0x18001b4c0`
- `0x18001b684`
- `0x18001bf4c`
- `0x180020ee8`
- `0x1800216f0`
- `0x1800227c0`
- `0x18002bf7c`
- `0x18002c01c`
- `0x18002c44c`
- `0x18002c804`
- `0x18002c9e8`
- `0x18002cc48`
- `0x18002cf74`
- `0x18002e660`
- `0x18002e7c0`
- `0x18002e8e0`
- `0x18002f050`
- `0x18002f9b0`
- `0x180030340`
- `0x1800304a0`
- `0x180030630`
- `0x180030e40`
- `0x180030f00`
- `0x180030fac`
- `0x1800311c0`
- `0x180031450`
- `0x180031940`
- `0x180031cc0`
- `0x1800328b0`
- `0x180032ac0`
- `0x180033660`
- `0x180033710`
- `0x180034084`

## callees

- `0x18002f05c`
- `0x180079760`

## import_xrefs

- `ntdll!RtlVirtualUnwind` at `0x18002f0f6`
- `ntdll!RtlVirtualUnwind` at `0x18002f0f6`
- `ntdll!RtlCaptureContext` at `0x18002f0a2`
- `ntdll!RtlCaptureContext` at `0x18002f0a2`
- `ntdll!RtlLookupFunctionEntry` at `0x18002f0b7`
- `ntdll!RtlLookupFunctionEntry` at `0x18002f0b7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002f11b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002f11b`

## pseudocode

```c
void __cdecl __noreturn invoke_watson(
        const wchar_t *Expression,
        const wchar_t *FunctionName,
        const wchar_t *FileName,
        unsigned int LineNo,
        uintptr_t Reserved)
{
  ULONG64 Rip; // rbx
  struct _RUNTIME_FUNCTION *v6; // rax
  unsigned __int64 ImageBase; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+48h] [rbp-B8h] BYREF
  PVOID HandlerData; // [rsp+50h] [rbp-B0h] BYREF
  CONTEXT ContextRecord; // [rsp+60h] [rbp-A0h] BYREF
  DWORD64 retaddr; // [rsp+548h] [rbp+448h] BYREF

  EstablisherFrame = 0;
  HandlerData = 0;
  ImageBase = 0;
  RtlCaptureContext(&ContextRecord);
  Rip = ContextRecord.Rip;
  v6 = RtlLookupFunctionEntry(ContextRecord.Rip, &ImageBase, 0);
  if ( v6 )
  {
    RtlVirtualUnwind(0, ImageBase, Rip, v6, &ContextRecord, &HandlerData, &EstablisherFrame, 0);
  }
  else
  {
    ContextRecord.Rip = retaddr;
    ContextRecord.Rsp = (DWORD64)&retaddr;
  }
  OutputDebugStringA("Invalid parameter passed to C runtime function.\n");
}

```

## disassembly

```asm
0x18002f05c  mov     [rsp-8+arg_0], rbx
0x18002f061  push    rbp
0x18002f062  lea     rbp, [rsp-440h]
0x18002f06a  sub     rsp, 540h
0x18002f071  mov     rax, cs:__security_cookie
0x18002f078  xor     rax, rsp
0x18002f07b  mov     [rbp+440h+var_10], rax
0x18002f082  lea     rcx, [rsp+540h+ContextRecord]; ContextRecord
0x18002f087  mov     [rsp+540h+var_4F8], 0
0x18002f090  mov     [rsp+540h+var_4F0], 0
0x18002f099  mov     [rsp+540h+ImageBase], 0
0x18002f0a2  call    cs:__imp_RtlCaptureContext
0x18002f0a8  mov     rbx, [rbp+440h+ContextRecord.Rip]
0x18002f0ac  lea     rdx, [rsp+540h+ImageBase]; ImageBase
0x18002f0b1  mov     rcx, rbx; ControlPc
0x18002f0b4  xor     r8d, r8d; HistoryTable
0x18002f0b7  call    cs:__imp_RtlLookupFunctionEntry
0x18002f0bd  test    rax, rax
0x18002f0c0  jz      short loc_18002F0FE
0x18002f0c2  mov     rdx, [rsp+540h+ImageBase]; ImageBase
0x18002f0c7  lea     rcx, [rsp+540h+var_4F8]
0x18002f0cc  mov     [rsp+540h+ContextPointers], 0; ContextPointers
0x18002f0d5  mov     r9, rax; FunctionEntry
0x18002f0d8  mov     [rsp+540h+EstablisherFrame], rcx; EstablisherFrame
0x18002f0dd  mov     r8, rbx; ControlPc
0x18002f0e0  lea     rcx, [rsp+540h+var_4F0]
0x18002f0e5  mov     [rsp+540h+HandlerData], rcx; HandlerData
0x18002f0ea  lea     rcx, [rsp+540h+ContextRecord]
0x18002f0ef  mov     [rsp+540h+var_520], rcx; ContextRecord
0x18002f0f4  xor     ecx, ecx; HandlerType
0x18002f0f6  call    cs:__imp_RtlVirtualUnwind
0x18002f0fc  jmp     short loc_18002F114
0x18002f0fe  mov     rax, [rbp+448h]
0x18002f105  mov     [rbp+440h+ContextRecord.Rip], rax
0x18002f109  lea     rax, [rbp+448h]
0x18002f110  mov     [rbp+440h+ContextRecord.Rsp], rax
0x18002f114  lea     rcx, OutputString
0x18002f11b  call    cs:__imp_OutputDebugStringA
0x18002f121  mov     rcx, [rbp+440h+var_10]
0x18002f128  xor     rcx, rsp; StackCookie
0x18002f12b  call    __security_check_cookie
0x18002f130  mov     rbx, [rsp+540h+arg_0]
0x18002f138  add     rsp, 540h
0x18002f13f  pop     rbp
0x18002f140  retn
```
